Follow the instructions to run a complete GenAI Stack using Docker Compose

## Table of Contents

- [Pre-req](#prereq)
- [Step 1. Install Ollama on Mac OS](#step-1-install-ollama-on-mac-os)
- [Step 2. Create OpenAI Secret API Keys](#step-2-create-openai-secret-api-keys)
- [Step 3. Sign up for LangChain Beta for API Keys](#step-3-sign-up-for-langchain-beta-for-api-keys)
- [Step 4. Clone the GenAI Repo](#step-4-clone-the-genai-repo)
- [Step 5. Create .env file](#step-5-create-.env-file)
- [Step 6. Bring up Compose Services](#step-6-bring-up-compose-services)
- [Step 7. Viewing the services on Docker Dashboard](#step-7-viewing-the-services-on-docker-dashboard)
- [Step 8. Accessing the app](#step-8-accessing-the-app)
- [Step 9. Accessing the Neo4j](#step-9-accessing-the-neo4j) 
- [Step 10. Accessing GenAI Stack PDF Bot](#step-10-accessing-genai-stack-pdf-bot) 



## Prereq

- [Install Docker Desktop 4.23.0](https://docs.docker.com/desktop/install/mac-install/)


## Step 1. Install Ollama on Mac OS



Visit [this link](https://ollama.ai/) to download and install Ollama on Macbook.
_Please note that currently, Windows is not supported by Ollama, so Windows users need to generate a OpenAI API key and configure the stack to use gpt-3.5 or gpt-4 in the .env file._

![Image2](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/vbn2gzk1wridnwo60bve.png)

Choose your preferrable operating system. 


![Image3](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/3ldzwwl9s7cqhhybacfy.png)


## Step 2. Create OpenAI Secret API Keys

Visit [this link](https://platform.openai.com/account/api-keys) to create your new OpenAI Secret API Keys.

## Step 3. Sign Up for LangChain Beta for API Keys

[Visit this link](https://www.langchain.com/langsmith) in order to create Langchain Endpoint and API Keys. You will need the following information

```
LANGCHAIN_ENDPOINT="https://api.smith.langchain.com"
LANGCHAIN_TRACING_V2=true # false
LANGCHAIN_PROJECT=default
LANGCHAIN_API_KEY=ls__cbabccXXXXXX
```

## Step 4. Clone the repository

```
 git clone https://github.com/docker/genai-stack
 cd genai-stack
```



## Step 5. Create .env file



```
cat .env 
OPENAI_API_KEY=sk-EsNJzI5uMBCXXXXXXXX
OLLAMA_BASE_URL=http://host.docker.internal:11434
NEO4J_URI=neo4j://database:7687
NEO4J_USERNAME=neo4j
NEO4J_PASSWORD=password
LLM=llama2 #or any Ollama model tag, or gpt-4 or gpt-3.5
EMBEDDING_MODEL=sentence_transformer #or openai or ollama

LANGCHAIN_ENDPOINT="https://api.smith.langchain.com"
LANGCHAIN_TRACING_V2=true # false
LANGCHAIN_PROJECT=default
LANGCHAIN_API_KEY=ls__cbabccXXXXXX
```

Don't forget to change "localhost" to "database" under NEO4J_URI entry.

## Step 6. Bring up Compose services

```
 docker compose up -d --build
```

```
..
..
genai-stack-bot-1         |   You can now view your Streamlit app in your browser.
genai-stack-bot-1         |
genai-stack-bot-1         |   URL: http://0.0.0.0:8501
genai-stack-bot-1         |
genai-stack-pdf_bot-1     |
genai-stack-pdf_bot-1     |   You can now view your Streamlit app in your browser.
genai-stack-pdf_bot-1     |
genai-stack-pdf_bot-1     |   URL: http://0.0.0.0:8503
genai-stack-pdf_bot-1     |
genai-stack-loader-1      |
genai-stack-loader-1      |   You can now view your Streamlit app in your browser.
genai-stack-loader-1      |
genai-stack-loader-1      |   URL: http://0.0.0.0:8502
genai-stack-loader-1      |
```

## Step 7. Viewing the Services on Docker Dashboard



![Image9](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/i4f9w0emxz783prwxp2k.png)

## Step 8. Accessing the app

Visit [http://0.0.0.0:8502](http://0.0.0.0:8502) to access the following:


![Image11](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/9meuijb9sctt417rt7m3.png)

Click "Import". It will take a minute or two to run the import. Most of the time is spent generating the embeddings. After or during the import you can click the link to `http://localhost:7474` and log in with username “neo4j” and password “password” as configured in docker compose. There, you can see an overview in the left sidebar and show some connected data by clicking on the “pill” with the counts.

The data loader will import the graph using the following schema.


![Image12](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/5pv8g4kymilf1xq0pybd.png)

## Result:


![Image13](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/agpcckqn261t69t6ukf4.png)

The graph schema for Stack Overflow consists of nodes representing Questions, Answers, Users, and Tags. Users are linked to Questions they’ve asked via the “ASKED” relationship and to Answers they’ve provided with the “ANSWERS” relationship. Each Answer is also inherently associated with a specific Question. Furthermore, Questions are categorized by their relevant topics or technologies using the “TAGGED” relationship connecting them to Tags.

## Step 9. Accessing the Neo4j

As instructed, open `http://localhost:7474` and log in with username “neo4j” and password “password” as configured in docker compose.

![Image14](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/mrnhfnctjh2ai2kbdeib.png)


## Step 10. Query the Imported Data via a Chat Interface Using Vector + Graph Search

This application server on `http://localhost:8501` has the classic LLM chat UI and lets the user ask questions and get answers.

There’s a switch called RAG mode where the user can rely either completely on the LLMs trained knowledge (RAG: Disabled), or the more capable (RAG: Enabled) mode where the application uses similarity search using text embedding and graph queries to find the most relevant questions and answers in the database.

Click "Highly ranked questions"


## Step 11. Accessing GenAI Stack PDF Bot

Open `http://0.0.0.0:8503/` on the browser to access the PDF Bot that allows you to chat with your PDF file.

![Image15](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/v8hs4fipvmvxerdp1e6z.png)

In order to test drive, I uploaded my latest resume and asked a quick question.  It responded back with the right answer. Amazing !!
 
