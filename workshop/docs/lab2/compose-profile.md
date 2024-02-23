# Compose Profile


## Clone the repository

```
 git clone https://github.com/dockersamples/docker-init-demos/
```

## Change directory to Python project

```
 cd docker-init-demos/python/compose-watch/sample
```

## Start the Compose services

Ensuring that you have stopped old compose services so as not to conflict between the listening ports

```
 docker compose --profile dev --file compose-profile.yaml up -d
```

The command will start just 2 services - Python and database.

Change dev to prod, and see if it starts all the listed services






