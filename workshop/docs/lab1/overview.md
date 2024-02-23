## What is GenAI?


Generative AI (GenAI) is a branch of artificial intelligence focused on creating new, original content by learning from vast amounts of data. This technology can generate text, images, audio, and more, mimicking the characteristics of the input data without directly replicating it. GenAI has seen significant advancements through models like Variational Autoencoders (VAEs), Generative Adversarial Networks (GANs), and transformers, which have enabled the production of complex and realistic outputs, pushing the boundaries of content creation and automation.

In real-world applications, GenAI is making strides across various industries, from entertainment and pharmaceuticals to manufacturing and finance. For instance, it's used in the entertainment industry for generating conceptual art and music for games and movies, while pharmaceutical companies leverage it for designing proteins for new medicines. Manufacturing sectors utilize GenAI for optimizing design processes in 3D printing and additive manufacturing, demonstrating GenAI's versatility in enhancing creativity, efficiency, and personalization across different fields.

The advent of Large Language Models (LLMs) has been a game-changer in the field of GenAI, particularly in text generation. Models like GPT (Generative Pre-trained Transformer) series by OpenAI have showcased the ability to generate human-like text, offering applications in customer support, content creation, and more. These LLMs are trained on diverse internet text, enabling them to produce coherent and contextually relevant text outputs based on prompts. The integration of LLMs into GenAI applications exemplifies the technology's potential in transforming communication, content generation, and interactive experiences.

These developments underscore the expansive potential of GenAI, from revolutionizing content creation to accelerating drug discovery and beyond, showcasing a future where AI-driven innovation is integral across sectors.

## What is GenAI Stack?


The GenAI Stack is a set of Docker containers that are orchestrated by Docker Compose which includes a management tool for local LLMs (Ollama), a database for grounding (Neo4j), and GenAI apps based on LangChain. The containers provide a dev environment of a pre-built, support agent app with data import and response generation use-cases. You can experiment with importing different information in the knowledge graph and examine how the variety in underlying grounding information affects the generated responses by the LLM in the user interface.

The GenAI Stack consists of:

- Application containers (the application logic in Python built with LangChain for the orchestration and Streamlit for the UI).
- Database container with vector index and graph search (Neo4j).
- LLM container Ollama (if you’re on Linux). If you’re on MacOS, install Ollama outside of Docker.

These containers are tied together with Docker compose. Docker compose has a watch mode setup that rebuilds relevant containers any time you make a change to the application code, allowing for fast feedback loops and a good developer experience.
