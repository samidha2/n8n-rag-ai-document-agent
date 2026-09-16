# System Architecture

## Overview

This project implements a Retrieval-Augmented Generation (RAG) based AI Document Agent using n8n.

The system combines document ingestion, Gemini embeddings, vector storage, semantic retrieval, an AI Agent, Gemini Chat Model, and conversational memory.

## High-Level Architecture

```text
Google Drive
     ↓
Download File
     ↓
Data Loader
     ↓
Gemini Embeddings
     ↓
Simple Vector Store
     ↓
AI Agent
     ├── Gemini Chat Model
     ├── Simple Memory
     └── Vector Store Tool
     ↓
Context-Aware Answer
1. Document Ingestion

Documents are retrieved from Google Drive and passed to the document processing pipeline.

Google Drive
     ↓
Download File
     ↓
Default Data Loader

The Data Loader prepares the document content for embedding and retrieval.

2. Embedding Generation

The document content is converted into vector representations using Gemini embeddings.

Document
    ↓
Text Extraction
    ↓
Document Chunks
    ↓
Gemini Embeddings
    ↓
Vector Representations

Embeddings represent the semantic meaning of text numerically and allow the system to perform semantic similarity searches.

3. Vector Store

The generated embeddings are stored in the Simple Vector Store.

Document Chunks
      ↓
Embeddings
      ↓
Simple Vector Store

When a user asks a question, relevant document information can be retrieved from the vector store.

4. AI Agent

The AI Agent acts as the orchestration layer of the system.

It is connected to:

Gemini Chat Model
Simple Memory
Simple Vector Store

The Agent can use the vector store to retrieve relevant document information before generating an answer.

5. Retrieval-Augmented Generation

The project follows the RAG architecture:

User Question
      ↓
Semantic Retrieval
      ↓
Relevant Document Chunks
      ↓
Retrieved Context
      ↓
Gemini Chat Model
      ↓
Generated Answer

RAG allows the language model to use information retrieved from the connected documents instead of relying only on its pre-trained knowledge.

6. Conversational Memory

Simple Memory maintains conversational context between interactions.

Example:

User:
What are the eligibility requirements?

AI:
The document specifies...

User:
What about the income requirement?

AI:
Based on the same document...

This enables follow-up questions to be interpreted in the context of the ongoing conversation.

7. Complete Data Flow
                ┌──────────────┐
                │ Google Drive │
                └──────┬───────┘
                       │
                       ▼
                ┌──────────────┐
                │ Download File│
                └──────┬───────┘
                       │
                       ▼
                ┌──────────────┐
                │ Data Loader  │
                └──────┬───────┘
                       │
                       ▼
                ┌──────────────┐
                │   Gemini     │
                │  Embeddings  │
                └──────┬───────┘
                       │
                       ▼
                ┌──────────────┐
                │ Vector Store │
                └──────┬───────┘
                       │
                       │ Retrieval
                       ▼
User Question ──► AI Agent
                       │
              ┌────────┴─────────┐
              ▼                  ▼
       Gemini Chat         Simple Memory
          Model
              │
              ▼
        Final Response
8. Technology Stack
Component	Technology
Workflow Orchestration - n8n
Document Source	- Google Drive
Document Processing -	n8n Data Loader
Embeddings - Google Gemini
Vector Storage - n8n Simple Vector Store
AI Agent - n8n AI Agent
Language Model - Google Gemini Chat Model
Memory - n8n Simple Memory
Architecture - Retrieval-Augmented Generation