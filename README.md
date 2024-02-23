![stars](https://img.shields.io/github/stars/sidagarwal04/genai-workshops-apac)
![Twitter](https://img.shields.io/twitter/follow/neo4j?style=social)




# Welcome to GenAI Stack Workshop



The GenAI Stack is a pre-configured, ready-to-code, and secure environment that makes it easy for developers to build and deploy GenAI applications.

The GenAI Stack is a collaborative effort launched by Docker, Neo4j, LangChain, and Ollama at DockerCon 2023, aimed at streamlining the development of generative AI applications. This stack integrates several cutting-edge technologies to provide developers with a comprehensive toolkit for building AI-powered applications with ease.

Gen-AI Stack Workshops are a series of workshops designed to teach developers how to build and deploy GenAI applications using the GenAI Stack. These workshops are ideal for developers who are interested in learning more about GenAI or who are looking for a hands-on introduction to the GenAI Stack.

These hands-on labs will be a combination of theory and practical exercises.

[Access the Workshop Here!](https://genai-workshops-apac.netlify.app/)

## Benefits of GenAI Stack Workshop

- Learn about GenAI and why it is important
- Learn how to use Docker to containerize and deploy GenAI applications
- Learn how to use Neo4j to store and manage knowledge graphs
- Learn how to use LangChain to generate text, translate languages, and write different kinds of creative content
- Learn how to use Ollama to train and deploy large language models
- Learn how to use the GenAI Stack to build and deploy GenAI applications
- Get hands-on experience with the GenAI Stack
- Network with other GenAI developers and trainers

## Contribution Guidelines

We welcome contributors to improve this lab workshop. 

### Running Lab using a Docker container

```
 docker run -d -p 8000:8000 ajeetraina/genai-workshop
```

Open your browser and access the lab via `http://localhost:8000`


### Building it from scratch

#### Clone the repository

``` 
 git clone https://github.com/sidagarwal04/genai-workshops-apac
 cd genai-workshops-apac/workshop
```

#### Install the prerequisite modules

``` 
 pip3 install -r requirements.txt
```

## Bringing up the site

``` 
mkdocs build
mkdocs serve
```
