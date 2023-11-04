## What is GenAI Stack?


The GenAI Stack is a set of Docker containers that are orchestrated by Docker Compose which includes a management tool for local LLMs (Ollama), a database for grounding (Neo4j), and GenAI apps based on LangChain. The containers provide a dev environment of a pre-built, support agent app with data import and response generation use-cases. You can experiment with importing different information in the knowledge graph and examine how the variety in underlying grounding information affects the generated responses by the LLM in the user interface.

The GenAI Stack consists of:

- Application containers (the application logic in Python built with LangChain for the orchestration and Streamlit for the UI).
- Database container with vector index and graph search (Neo4j).
- LLM container Ollama (if you’re on Linux). If you’re on MacOS, install Ollama outside of Docker.

These containers are tied together with Docker compose. Docker compose has a watch mode setup that rebuilds relevant containers any time you make a change to the application code, allowing for fast feedback loops and a good developer experience.
