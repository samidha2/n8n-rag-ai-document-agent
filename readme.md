# 🤖 n8n RAG AI Document Agent

An AI-powered document question-answering system built using **n8n, Retrieval-Augmented Generation (RAG), Google Drive, Gemini, embeddings, vector search, and conversational memory**.

The system allows users to interact with documents through a conversational AI agent. Documents are ingested, converted into embeddings, stored in a vector database, and retrieved dynamically when the user asks a question.

---

## 🚀 Project Overview

Traditional document search requires users to manually search through large documents.

This project uses a **Retrieval-Augmented Generation (RAG)** architecture to allow users to ask natural-language questions about their documents.

The workflow:

1. Retrieves documents from Google Drive
2. Loads and processes the document
3. Splits document content into usable text
4. Generates vector embeddings using Gemini
5. Stores embeddings in a vector store
6. Receives user questions through an AI Agent
7. Retrieves relevant document information
8. Sends the retrieved context to the Gemini language model
9. Generates a natural-language response
10. Maintains conversational context using memory

---

## 🧠 Architecture

```text
                 ┌─────────────────┐
                 │   Google Drive  │
                 │    Documents    │
                 └────────┬────────┘
                          │
                          ▼
                 ┌─────────────────┐
                 │  Download File │
                 └────────┬────────┘
                          │
                          ▼
                 ┌─────────────────┐
                 │  Data Loader    │
                 └────────┬────────┘
                          │
                          ▼
                 ┌─────────────────┐
                 │ Gemini          │
                 │ Embeddings      │
                 └────────┬────────┘
                          │
                          ▼
                 ┌─────────────────┐
                 │ Vector Store    │
                 │ Retrieval       │
                 └────────┬────────┘
                          │
                          │
User Question ────────────┤
                          ▼
                 ┌─────────────────┐
                 │    AI Agent     │
                 └────────┬────────┘
                          │
              ┌───────────┴───────────┐
              ▼                       ▼
      ┌───────────────┐       ┌───────────────┐
      │ Gemini Chat   │       │ Conversation  │
      │ Model         │       │ Memory        │
      └───────────────┘       └───────────────┘
                          │
                          ▼
                 ┌─────────────────┐
                 │ Final Answer    │
                 └─────────────────┘