# AI RAG Chatbot Learning Material

This repository is a hands-on learning project for building LangGraph-based chatbots with Google Gemini, RAG, tool use, and optional MCP integration.

## What is included

The project demonstrates several chatbot patterns:

- a basic LangGraph chatbot with Gemini
- a database-backed version with SQLite checkpoint persistence
- a tool-enabled chatbot that can call external functions such as web search, arithmetic, and stock lookup
- a RAG-enabled chatbot that can ingest PDF documents and answer questions from them
- an MCP-enabled chatbot backend for multi-process/custom tool execution
- Streamlit frontends for each workflow, including chat history, threaded conversations, and PDF upload

## Project structure

- [langgraph_backend.py](langgraph_backend.py) - Simple LangGraph chatbot workflow using Gemini.
- [langgraph_database_backend.py](langgraph_database_backend.py) - SQLite-backed conversation persistence.
- [langgraph_tool_backend.py](langgraph_tool_backend.py) - Tool-enabled chatbot with search, calculator, and stock lookup tools.
- [langgraph_rag_backend.py](langgraph_rag_backend.py) - RAG-enabled chatbot with PDF ingestion and document retrieval.
- [langgraph_mcp_backend.py](langgraph_mcp_backend.py) - MCP-enabled backend for external tool adapters and async tool orchestration.
- [streamlit_frontend.py](streamlit_frontend.py) - Basic Streamlit chat UI.
- [streamlit_frontend_database.py](streamlit_frontend_database.py) - Streamlit UI with database-backed conversation history.
- [streamlit_frontend_tool.py](streamlit_frontend_tool.py) - Streamlit UI for the tool-enabled chatbot with visible tool activity.
- [streamlit_frontend_rag.py](streamlit_frontend_rag.py) - Streamlit UI for RAG with PDF upload and retrieval per chat thread.
- [streamlit_frontend_mcp.py](streamlit_frontend_mcp.py) - Streamlit UI for the MCP-enabled chatbot.
- [environment.yml](environment.yml) - Conda environment configuration.

## Prerequisites

Before running the project, make sure you have:

- Python 3.11
- Conda or Miniconda
- A Google Gemini API key

## Installation

1. Create and activate the environment:

```
conda env create -f environment.yml
conda activate ai-rag-chatbot-learning
```

2. Create a `.env` file in the project root with your credentials:

```
GEMINI_API_KEY=your_gemini_api_key
GEMINI_MODEL=gemini-3.1-flash-lite
```

3. Install any additional dependencies if needed:

```
pip install -r requirements.txt
```

> The project currently depends on `streamlit`, `langgraph`, `langchain`, `langchain-core`, `langchain-google-genai`, `python-dotenv`, and `langgraph-checkpoint-sqlite`.

## Running the app

### Basic version

```
streamlit run streamlit_frontend.py
```

### Database-backed version

```
streamlit run streamlit_frontend_database.py
```

### Tool-enabled version

```
streamlit run streamlit_frontend_tool.py
```

### RAG-enabled version

```
streamlit run streamlit_frontend_rag.py
```

### MCP-enabled version

```
streamlit run streamlit_frontend_mcp.py
```

## Features

### RAG backend

- upload PDF documents per chat thread
- create an embedding-based FAISS retriever for document search
- answer questions using retrieved document context
- maintain thread-specific document metadata and history

### Tool-enabled backend

- DuckDuckGo web search
- arithmetic calculations
- stock price lookup via Alpha Vantage
- tool usage visible in the Streamlit UI

### MCP backend

- connect to external MCP tool servers
- support async tool orchestration
- integrate custom MCP tool adapters into the chatbot workflow

## Notes

- The `.env` file is intentionally excluded from version control to protect sensitive credentials.
- If Gemini model availability changes, update the `GEMINI_MODEL` value in your `.env` file.
- The project currently uses a local SQLite checkpoint store for persistence in database-backed and RAG workflows.

## License

This project is intended for educational and learning purposes.
