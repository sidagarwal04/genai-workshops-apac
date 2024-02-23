## Compose Watch

Use watch to automatically update and preview your running Compose services as you edit and save your code. Compose Watch is available in Docker Compose version 2.22 and later.

## Clone the repository

```
 git clone https://github.com/dockersamples/docker-init-demos
```

## Change to the python directory

```
 cd docker-init-demos/python/compose-watch
```

## Copy the necessary files from samples directory

```
 cp -rf samples/Dockerfile .
 cp -rf samples/compose.yaml .
```

## Start the Compose Watch

```
 docker compose watch
```

Keep the terminal open. Open a new terminal and make some changes in the requirements.txt:


```
 flask
 gunicorn
```

Examine the compose watch terminal to see how it rebuilds the application automatically.

You will see that compose watch monitors the file system change and rebuilds it automatically.
