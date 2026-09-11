# Lessons Index (Centralized, Tagged)

Generalizable, reusable rules promoted from per-task `<tasks-dir>/<task-id>/lessons-learned.md`.
Per-task files remain the write-time audit trail; this file is the **read-before** source.

## How to use

- **Read-before**: `grep` this file by the tags that match your work, e.g. `agent:executor`, `stack:<your-stack>`, `repo:<your-repo>`. Read only matching lines — do not scan every task folder.
- **Promote (write-after)**: after writing your per-task lessons, if a lesson is generalizable or has recurred, add a one-line entry here with a tag comment. Keep task-specific noise in the per-task file only.

## Tag format

`<!-- agent:<name[,name]> repo:<repo|any> stack:<stack|any> type:<category> -->`

- `agent`: one or more of `planner`, `executor`, `repo-indexer`, `reviewer` (comma-separated when a rule applies to several).
- `repo`: the repository the rule is specific to, or `any`.
- `stack`: the tech/tool the rule is specific to (e.g. `terraform`, `python`, `dotnet`, `node`, `aws`), or `any`.
- `type`: a category from the list below.

Categories: `scoping`, `process`, `verification`, `design`, `sizing`, `deployment`, `testing`, `consistency`, `completeness`, `repo-fact`.

---

## Planner

<!-- Promoted planning lessons go here. Example:
- Verify file paths against the filesystem; don't trust doc paths verbatim. <!-- agent:planner repo:any stack:any type:verification -->
-->

## Executor

<!-- Promoted execution lessons go here. Example:
- When following "use existing pattern from X", diff your new resource against the original and flag any dropped attributes. <!-- agent:executor repo:any stack:any type:completeness -->
-->

## Repo-indexer

<!-- Promoted indexing lessons go here. Example:
- Preserve "how/why it works" explanations; update only factual details (versions, names, paths, counts). <!-- agent:repo-indexer repo:any stack:any type:consistency -->
-->

## Reviewer

> Correction-driven reviewer learnings live in `<tasks-dir>/pr-review-learnings.md`. Cross-agent rules above also apply.

## Repo facts

<!-- Durable, repo-specific facts (build quirks, path conventions, generated files) go here, tagged with the specific repo. -->
