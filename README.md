# AI RAG Chatbot Learning Material

This repository is a hands-on learning project for building a LangGraph-based chatbot with Google Gemini, Streamlit, tool use, and optional observability with LangSmith.

## What is included

The project demonstrates several chatbot patterns:

- a basic LangGraph chatbot with Gemini
- a database-backed version with SQLite checkpoints
- a tool-using version that can call external functions such as web search, arithmetic, and stock lookup
- a Streamlit frontend with chat history and thread-based conversations
- optional LangSmith tracing for observability during runs

## Project structure

- [langgraph_backend.py](langgraph_backend.py) - Simple chatbot workflow using LangGraph and Gemini.
- [langgraph_database_backend.py](langgraph_database_backend.py) - Same workflow but with SQLite-based persistence for conversation threads.
- [langgraph_tool_backend.py](langgraph_tool_backend.py) - Tool-enabled chatbot with search, calculator, and stock price tools.
- [streamlit_frontend.py](streamlit_frontend.py) - Basic Streamlit chat UI.
- [streamlit_frontend_database.py](streamlit_frontend_database.py) - Streamlit UI with database-backed conversation history.
- [streamlit_frontend_tool.py](streamlit_frontend_tool.py) - Streamlit UI for the tool-using chatbot with visible tool activity.
- [environment.yml](environment.yml) - Conda environment configuration.

## Prerequisites

Before running the project, make sure you have:

- Python 3.11
- Conda or Miniconda
- A Google Gemini API key
- Optional: a LangSmith API key if you want tracing enabled

## Installation

1. Create and activate the environment:

```bash
conda env create -f environment.yml
conda activate ai-rag-chatbot-learning
```

2. Create a `.env` file in the project root with your credentials:

```env
GEMINI_API_KEY=your_gemini_api_key
GEMINI_MODEL=gemini-3.1-flash-lite
```

Optional LangSmith variables:

```env
LANGSMITH_TRACING=true
LANGSMITH_API_KEY=your_langsmith_api_key
LANGCHAIN_PROJECT=ai-rag-chatbot-learning
```

> If you run the tool-based backend, make sure the `langchain-community` package is available in your environment.

## Running the app

### Basic version

```bash
streamlit run streamlit_frontend.py
```

### Database-backed version

```bash
streamlit run streamlit_frontend_database.py
```

### Tool-enabled version

```bash
streamlit run streamlit_frontend_tool.py
```

## Features in the tool-enabled backend

The tool-based workflow supports:

- DuckDuckGo web search
- arithmetic calculations
- stock price lookup via an external API

The frontend shows tool usage status while the assistant is reasoning and calling tools.

## Notes

- The `.env` file is intentionally excluded from version control to protect sensitive credentials.
- If Gemini model availability changes, update the `GEMINI_MODEL` value in your `.env` file.
- LangSmith tracing is optional and can be enabled for debugging and monitoring agent behavior.

## License

This project is intended for educational and learning purposes.
