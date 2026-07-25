# AI RAG Chatbot Learning Material

This project demonstrates a simple conversational AI application built with Streamlit and LangGraph, powered by Google Gemini.

## Overview

The repository contains a lightweight chatbot architecture composed of:

- a backend graph workflow implemented with LangGraph
- a frontend interface built with Streamlit
- environment-based configuration for the Gemini API key and model selection

## Project Structure

- `langgraph_backend.py` - Defines the LangGraph chatbot workflow and Gemini model integration.
- `streamlit_frontend.py` - Provides the Streamlit user interface for chatting with the model.
- `environment.yml` - Conda environment configuration for installing project dependencies.
- `.env` - Stores local environment variables such as the Gemini API key.
- `.gitignore` - Prevents sensitive files such as `.env` from being committed to GitHub.

## Prerequisites

Before running the project, ensure you have the following installed:

- Python 3.11
- Conda or Miniconda
- A valid Google Gemini API key

## Installation

1. Create and activate the Conda environment:

```bash
conda env create -f environment.yml
conda activate ai-rag-chatbot-learning
```

2. Configure your environment variables:

Create or update the `.env` file in the project root with the following values:

```env
GEMINI_API_KEY=your_api_key_here
GEMINI_MODEL=gemini-1.5-flash
```
## Running the Application

Start the Streamlit frontend:

```bash
streamlit run streamlit_frontend.py
```
This will launch the chatbot interface in your browser.

## Notes

- The `.env` file is intentionally excluded from version control to protect your API credentials.
- If you encounter model availability issues, update the `GEMINI_MODEL` value in the `.env` file to a supported Gemini model.

## License
This project is intended for educational and learning purposes.
