# Artificial-Intelligence
Tools in the market agentic AI
1.	Crewai (multi agent platform) : No code environment
2.	Make.com
3.	N8n.io
4.	Zapier.com
5.	Huggingface.com
6.	Console.groq.com : To test your prompt skill
7.	Replit.com
8.	Hostinger : ai
9.	VS code Augmented code extension.
--------------
AI Training:
Day 1 — Foundations:

AI -> ML -> DL
  
ML vs DL
(Structured data, small data, need CPU) vs (Image, audio, video, larger data, need GPU’s)

Traditional Machine Learning:
Structured Data, Numeric Data, Existing Dataset Training
Observe and Analyze, 

Linear Regression: Regression is a statistical and machine learning technique used to model and analyze the relationship between a dependent variable (target) and one or more independent variables (predictors). The goal is to predict or estimate the dependent variable based on the values of the independent variables.
dependent and independent variables calculate the MSE.
MSE mean square error (*Reducing the error)
Training set and Test Set (70-30, 75-25, 80-20%)
Numpy python lib
Logistic Regression:  is a statistical and machine learning technique used for classification problems, not regression in the traditional sense. Despite its name, it predicts categorical outcomes (like Yes/No, 0/1, Spam/Not Spam) rather than continuous values.
 
(Possibilities and probabilities)

#Decision Tree: A Decision Tree is a supervised machine learning algorithm used for both classification and regression tasks. It works by splitting data into branches based on feature values, forming a tree-like structure where each internal node represents a decision on a feature, each branch represents an outcome, and each leaf node represents a final prediction.
	#Entropy, Gini index, Information Gain
	#Feature Scaling: 
#Decision Tree classification
#Making the confusion matrix
Accuracy formula 
	Accuracy =  TP +TN/TP+TN+FP+FN
# between 75-92%
#

#Overfitting, Underfitting
#Random Forest:  Majority voting
#Confusion metric:
#Volume of Data 
#Feature Selection

3. Deep Learning: (One activity in Depth)
Neural Networks, Activation Functions, Feed Forward mechanism,
Tensorflow lib (neural n/w lib)
LabelEncoder

# The AI Landscape for Developers:
Orchestration
https://spacy.io/usage/spacy-101
#Generative AI: generates new content or data.
Name	Description
Tokenization	Segmenting text into words, punctuations marks etc.
Part-of-speech (POS) Tagging	Assigning word types to tokens, like verb or noun.
Dependency Parsing	Assigning syntactic dependency labels, describing the relations between individual tokens, like subject or object.
Lemmatization	Assigning the base forms of words. For example, the lemma of “was” is “be”, and the lemma of “rats” is “rat”.
Sentence Boundary Detection (SBD)	Finding and segmenting individual sentences.
Named Entity Recognition (NER)	Labelling named “real-world” objects, like persons, companies or locations.
Entity Linking (EL)	Disambiguating textual entities to unique identifiers in a knowledge base.
Similarity	Comparing words, text spans and documents and how similar they are to each other.
Text Classification	Assigning categories or labels to a whole document, or parts of a document.
Rule-based Matching	Finding sequences of tokens based on their texts and linguistic annotations, similar to regular expressions.
Training	Updating and improving a statistical model’s predictions.
Serialization	Saving objects to files or byte strings.

#Large Language Model (LLM): in AI refers to a type of deep learning model trained on massive amounts of text data to understand and generate human-like language. These models are the backbone of modern Natural Language Processing (NLP) applications.

#How the content is Orchestrated: 
	
#Prompt Engineering:

1.	Instructional & Zero-shot Promting.
2.	Few-shot & Chain-of-thought Prompting
3.	Role & Contextual Prompting
4.	Prompt Chaining & Multi-modal Prompting
5.	System Prompting & Self-Consistency Prompting
6.	Advanced Techniques: Retrieval-Augmented & Constitutional Prompting

#Day 2 — RAG (Retrieval-Augmented Generation) Deep Dive + LLM internals:

RAG Model: 
Uploading documentation and getting questions answered.

#What is vector database:  having multi dimension space having text to text information in binary form.
#Vector Embeddings:
#Cosine similarity, Euclidean Distance, Dot Product
#Vector DB : tools vendors Pinecone, Milvus, Weaviate, Chroma

#What is Agentic AI?

RAG Practice : https://github.com/writersrinivasan/RAG_Medium_HR
#Advanced RAG Model:

Create an advanced RAG model using supabase.
https://supabase.com/dashboard/sign-in?returnTo=%2Forg
https://vercel.com/

Vercel.app for web deployment

Create an advanced RAG model using supabase and host it in localhost

# Day 3 — Agentic Use Cases, Projects, MCP and Best Practices:
Example Agentic AI: rabbit.tech (H/W & S/W)
Agentic AI automates entire workflow not just isolated task.
# Use Cases for Agentic AI:
	Practical Use case for Agentic AI:
	Workflow creation

#EX: CFO dashboard where vendor payments processed automatically overnight.
#Ex: Automated Review, 

Example: Multi Agent platform :
1. augmentcode.com
2. Cursor.com
3. http://partyrock.aws/  (text to text project development)
4. Cruwai.com


# Model Context Protocol (MCP): Connecting AI to real world.
Its open shource
Its Universal Connector like UBS type c port. Its light weight.
Code simplification
#MCP Host : ex VS code
#MCP Client: Docker
#MCP Server: ex Github
#Local/Remote Resources : Actual api’s and datasource

https://modelcontextprotocol.io

Usecase: Customer Support Automation, Code review and PR raising with improvised code suggestion. 
 
Github token : Token_For_MCP
ghp_MfZ......
deleted token 


# Best Practices for AI-Powered Development:
CI/CD, Deployment Patterns & Monitoring

#Understanding LangChain: Simple AI workflow for everyone
(Maintain history)
Ex: Customer support chatbot (airtel cs)


Tools in the market agentic AI
1.	Crewai (multi agent platform) : No code environment
2.	Make.com
3.	N8n.io
4.	Zapier.com
5.	Huggingface.com
6.	Console.groq.com : To test your prompt skill
7.	Replit.com
8.	Hostinger : ai
9.	


ANN
Natural Language Processing (NLP) : project sentiment analysis
LSTM
HITL
GPU Infrastructure

Practice Set :

1. Smart Customer Support Triage (Multi-Agent)
Goal:
Automatically route customer queries to the right department and generate a response draft.
Agents

Intake Agent: Receives and cleans the query
Classifier Agent: Identifies category (Billing, Technical, General)
Knowledge Agent: Retrieves relevant FAQ or policy
Response Agent: Drafts a reply

Tech (Suggested)
Python, simple rules or lightweight LLM calls, in-memory store.
Acceptance Criteria

Query is classified correctly
A response draft is produced
Agents communicate via messages

Tests

Unit Tests:

Test classification logic with sample queries
Test message passing between agents


Scenario Tests:

End-to-end query flow from intake to response
Edge case: Unknown category




2. Multi-Agent Task Planner for Daily Work
Goal:
Convert a user’s goal into an ordered task plan with estimates.
Agents

Goal Interpreter Agent: Parses user input
Task Decomposer Agent: Breaks goal into tasks
Estimator Agent: Assigns time estimates
Reviewer Agent: Validates task completeness

Tech (Suggested)
Python, JSON message exchange.
Acceptance Criteria

Input goal produces a task list
Tasks include dependencies and time estimates

Tests

Unit Tests:

Goal parsing test
Task decomposition rules test


Scenario Tests:

Full flow for “Build a simple web app”
Handling vague goals




3. Intelligent Resume Screening System
Goal:
Evaluate resumes against a job description using multiple agents.
Agents

Resume Parser Agent
Skill Matching Agent
Scoring Agent
Decision Agent: Shortlist or Reject

Tech (Suggested)
Python, text files, simple scoring logic.
Acceptance Criteria

Resume score is generated
Decision logic is explainable

Tests

Unit Tests:

Skill extraction accuracy
Score calculation correctness


Scenario Tests:

Strong vs weak resume comparison
Missing skills handling




4. Multi-Agent News Verification Assistant
Goal:
Assess whether a news snippet is likely reliable.
Agents

Claim Extraction Agent
Cross-Check Agent: Looks for corroboration
Bias Detection Agent
Verdict Agent

Tech (Suggested)
Python, mock data sources.
Acceptance Criteria

Claims are extracted
Reliability verdict is produced

Tests

Unit Tests:

Claim extraction test
Bias scoring test


Scenario Tests:

Verified news example
Sensational headline example




5. Smart Inventory Replenishment System
Goal:
Recommend stock replenishment decisions.
Agents

Demand Forecast Agent
Inventory Monitor Agent
Supplier Selection Agent
Order Recommendation Agent

Tech (Suggested)
Python, CSV data.
Acceptance Criteria

Reorder recommendations generated
Stock-out conditions detected

Tests

Unit Tests:

Forecast logic test
Threshold detection test


Scenario Tests:

Sudden demand spike
Low inventory warning




6. Multi-Agent Code Review Assistant
Goal:
Analyze code quality collaboratively.
Agents

Style Checker Agent
Security Review Agent
Performance Review Agent
Summary Agent

Tech (Suggested)
Python, static rules, sample code files.
Acceptance Criteria

Issues detected by each agent
Unified review summary produced

Tests

Unit Tests:

Rule-based detection tests
Aggregation logic test


Scenario Tests:
Clean code input
Vulnerable code input
	
-------
