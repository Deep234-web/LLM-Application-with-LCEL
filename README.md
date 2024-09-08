# LLM-Application-with-LCEL

# Langchain FastAPI Translation Server

## Project Overview

This project demonstrates a simple API server built with FastAPI, utilizing Langchain to run a translation chain. The chain takes user input, applies a translation prompt template, and leverages the Groq `Gemma2-9b-It` model to perform the translation.

## Key Features

1. **FastAPI Integration**:
   - Provides an API server with a `/chain` endpoint for handling translation requests.
   - Uses FastAPI for easy and fast HTTP interface creation.

2. **Langchain Integration**:
   - The core translation logic is implemented using Langchain’s `ChatPromptTemplate` and the `ChatGroq` model.
   - A simple chain is built by combining the prompt template, model, and an output parser.

3. **Groq Model**:
   - Uses the `Gemma2-9b-It` model from Groq, with the API key being managed through environment variables.
   
4. **LangServe**:
   - The `add_routes` method from `langserve` is used to automatically generate and add routes for the translation chain.

## Key Components

1. **Environment Setup**:
   - Uses environment variables to manage the Groq API key:
     - `GROQ_API_KEY`
   - The key is loaded using Python’s `dotenv` package for secure management.

2. **Prompt Template**:
   - A translation prompt template is defined using `ChatPromptTemplate`:
     - The system message asks to "Translate the following into {language}:"
     - The user message dynamically accepts `{text}` to be translated.

3. **LLM (Groq - Gemma2-9b-It)**:
   - The model used for the translation task is `Gemma2-9b-It` from Groq, a large language model accessed via the Groq API.
   - The Groq API key is required for accessing the model.

4. **FastAPI App**:
   - A FastAPI app is created with a single endpoint `/chain` which invokes the translation chain.
   - The server can be run locally using Uvicorn.
