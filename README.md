# Blog Generation Bot

A project to generate blog posts (and translations) automatically using LangGraph, Groq/LLM integrations, and structured output schemas.

## 🚀 Features

- Graph-based workflow via **LangGraph**  
- Title generation, content generation, translation nodes  
- Structured output (title + content) via LLM wrappers  
- Multi-language support (e.g. French translation)  
- FastAPI backend to expose endpoints for blog creation  
- Modular architecture: states, nodes, graph builder  

## 🧱 Key Components

- **GraphBuilder**: constructs a directed flow graph (START → title → content → END or optional translation)  
- **BlogNode**: contains the logic for each step (title, content, translate)  
- **FastAPI** endpoint `POST /blogs` handles incoming requests and runs graph  
- **Structured output**: the LLM is instructed to produce output matching the `Blog` schema (e.g. `{"title": "...", "content": "..."}`)  

## 📦 Setup & Installation

1. Clone the repo:

   ```bash
   git clone https://github.com/yourusername/Blog-Generation-Bot.git
   cd Blog-Generation-Bot

2. Create and activate a virtual environment (Python 3.10+ recommended):
   ```bash
   python -m venv .venv
   source .venv/bin/activate   # Unix / macOS
   .venv\Scripts\activate      # Windows

3. Install dependencies:
   ```bash
   pip install -r requirements.txt

4. Create a .env file:
   ```bash
   OPENAI_API_KEY=your_openai_api_key
   GROQ_API_KEY=your_groq_api_key
   LANGCHAIN_API_KEY=your_langchain_key
6. Run the FastAPI server with Uvicorn
   ```bash
   uvicorn app:app --reload

