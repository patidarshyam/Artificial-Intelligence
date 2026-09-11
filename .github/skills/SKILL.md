---
name: example-service-local-run
description: "EXAMPLE SKILL (generic, non-proprietary). Self-contained knowledge for running a backend service locally against a shared dev environment, with no external doc required. Copy this file as a template when authoring your own self-contained skill. Use when a repeatable, hard-won setup needs to be captured so an agent can reproduce it without re-discovery."
---

# Example: Run a Service Locally (Self-Contained Knowledge)

> **This is a template/example skill.** It shows the recommended shape of a *self-contained* SKILL.md:
> every prerequisite, command, expected output, and fix lives here so an agent needs **no external
> reference**. Replace the angle-bracket markers (`<service>`, `<repo>`, `<dev-host>`, …) with your own
> values and delete anything that doesn't apply. Keep it concrete — a good skill reads like a runbook,
> not a tutorial.

This skill contains **everything** needed to run `<service>` locally against the shared **dev**
environment, using the local source instead of a published package.

> **Goal:** Start `<service>` on your machine, point it at the dev backend, exercise one request
> end-to-end, and see the expected response — with **no writes to shared/production data**.

---

## When to use / when not to use

- **Use** when: setting up `<service>` locally for the first time, or fixing a broken local setup.
- **Do not use** for: deploying to a shared environment, running against production, or any task that
  writes to shared data stores.

---

## 0. Choose your path

There are two ways to apply the local-run configuration:

- **Config file available** — if the team keeps a ready `<service>.local.env` (or equivalent), ask for
  its path and use it, then do the manual-only steps below.
- **No config file** — perform the **full manual setup** using the exact values in §3. This is the
  default and needs no external files.

Always ask the user first: **"Do you have a local-run config file? (yes → provide path; no → I'll set it
up manually)."**

---

## 1. Prerequisites

| Item | Value / Notes |
|------|---------------|
| OS / shell | Cross-platform. Commands below show **PowerShell** and **bash/zsh** variants. |
| Runtime | `<runtime + version>` (e.g. Node 20 / Python 3.12 / .NET 8). Verify with `<version-check cmd>`. |
| Package source | `<package registry/feed>` (network access required). |
| Credentials | Dev account/profile `<profile-name>`, region `<region>` — read-only where possible. |
| Layout | `<repo>` checked out; any sibling local packages under the same parent folder. |

> **Source of truth:** trust the actual manifest (`package.json` / `pyproject.toml` / `*.csproj`) for the
> runtime version — verify before building rather than assuming.

If the runtime is missing, install it (a system-wide install may need admin — confirm first), then use a
fresh terminal so `PATH` is refreshed.

---

## 2. How the app selects the environment

- Environment is selected by an env var, e.g. `APP_ENV` (defaults to `dev` when unset).
- The app loads `"<APP_ENV>.config.json"` (or `.env.<APP_ENV>`) from the working directory.
- Therefore **run from the directory that contains the resolved config** so the file is found.

Document *your* real mechanism here — the exact var name, file name, and load order — so nobody has to
re-read the source to figure it out.

---

## 3. Local-run configuration (exact values)

List every setting the local run needs. Be exact; a skill earns its keep by removing guesswork.

```dotenv
APP_ENV=dev
<SERVICE>_BASE_URL=https://<dev-host>/api
DB_MODE=read-only          # never point local runs at a writable shared DB
FEATURE_UPLOADS=false      # disable side-effects that touch shared storage
LOG_LEVEL=debug
```

**Manual-only edits not covered by any config file:**
1. `<file/line>` — `<what to change and why>` (e.g. bypass an auth gate that expects a real gateway).
2. `<file/line>` — swap a published dependency for the local source project reference.

---

## 4. Build & run

Disable pagers first so nothing blocks on `-- More --`:

- PowerShell: `$env:PAGER='cat'; $env:GIT_PAGER='cat'`
- bash/zsh: `export PAGER=cat GIT_PAGER=cat`

Then:

```bash
# from <repo>/<service>
<install cmd>            # e.g. npm ci  /  pip install -e .  /  dotnet restore
<build cmd>             # e.g. npm run build  /  (n/a)  /  dotnet build
<run cmd>              # e.g. npm start  /  python -m <service>  /  dotnet run
```

> Run from the **output/working directory** that contains the resolved config (see §2).

---

## 5. Expected output (what success looks like)

Spell out the concrete signal so the agent knows it worked:

```text
[info] <service> listening on http://localhost:<port>
[info] env=dev  db=read-only  uploads=disabled
```

Exercise one request end-to-end and show the expected response:

```bash
curl -s http://localhost:<port>/healthz          # -> {"status":"ok","env":"dev"}
curl -s http://localhost:<port>/api/<sample>     # -> <expected shape of the response>
```

Success criteria: healthz returns `ok`, the sample request returns `<expected>`, and **no** writes hit
shared storage (uploads disabled, DB read-only).

---

## 6. Troubleshooting

| Symptom | Likely cause | Fix |
|---------|--------------|-----|
| `config not found` on startup | Ran from the wrong directory | Run from the dir containing `<APP_ENV>.config.json` (§2) |
| `401 / 403` calling the dev API | Missing/expired dev credentials | Refresh `<profile-name>`; confirm the token/role is valid |
| Uses the published package, not local source | Project reference not swapped | Apply the manual project-reference edit (§3, manual edit 2) |
| Package restore fails | No access to `<package registry/feed>` | Confirm network/VPN and feed auth |
| Writes appear in shared storage | Side-effects not disabled | Set `FEATURE_UPLOADS=false` / `DB_MODE=read-only` (§3) |

---

## 7. Authoring checklist (delete after you adapt this)

A good self-contained skill:
- [ ] Frontmatter `name` + `description` — description states **what it does** and **when to use it**.
- [ ] States the **goal** and the **safety boundary** (no shared/prod writes) up front.
- [ ] Lists **exact** prerequisites, config values, and commands — no "figure it out".
- [ ] Shows **expected output** so success is unambiguous.
- [ ] Has a **troubleshooting** table for the failures you actually hit.
- [ ] Is **self-contained** — no dependency on an external doc that might move or go stale.
- [ ] Uses shell-agnostic commands (PowerShell + bash) where a shell is involved.
