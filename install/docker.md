---
title: Docker Installation
description: Launch Teamlock Stack using Docker
published: true
date: 2022-05-19T13:41:05.673Z
tags: docker, install
editor: markdown
dateCreated: 2022-05-11T12:01:42.649Z
---

> Before proceeding, make sure you meet the [system requirements](/install/requirements).
{.is-info}

# Using the Docker image

An image is available on [Docker Hub](https://hub.docker.com/repository/docker/raznak/teamlock).

## Environment Variables

All variables are required for Teamlock to works.

### General

- **APP_URL** : Instance URL of the Application. Will be used in email links
- **SECRET_KEY** : Secret Key for the instance. Will be used to encrypt all sessions data
- **LOG_LEVEL** : [default: INFO] Log Level
{.grid-list}

### Mail

- **SMTP_HOST** : URL of the SMTP Server *(e.g `smtp.gmail.com`)*
- **SMTP_PORT** : Port of the SMTP Server *(e.g `port`)*
- **SMTP_AUTH** : SMTP Server requires authentication *(e.g `true`)*
- **SMTP_EMAIL** : SMTP User (required if SMTP_AUTH is **true**)
- **SMTP_PASSWORD** : SMTP Password (required if SMTP_AUTH is **true**)
- **SMTP_SSL**: SMTP SSL *(e.g `true`)*
{.grid-list}

### Database

- **MONGO_HOST** : Mongo URL *(e.g `mongodb://127.0.0.1:27017`)*
- **MONGO_DATABASE** : Mongo Database Name
- **MONGO_USER** : [Optional] Username for mongodb authentication
- **MONGO_PASSWORD** : [Optional] Password for mongodb authentication
- **MONGO_AUTHSOURCE** : [Optional] Database to authenticate against
- **MONGO_REPLICASET** : [Optional] ReplicaSet Name
- **MONGO_TLS** : [Optional] **true/false**
- **MONGO_CA_FILE** : [Optional] CA File for TLS
- **MONGO_KEY_FILE** : [Optional] Certificate File for TLS
- **MONGO_ALLOW_INVALID_HOSTNAMES** : [Optional] **true/false**
- **MONGO_ALLOW_INVALID_CERTIFICATES** : [Optional] **true/false**
{.grid-list}

### Redis

- **REDIS_HOST** : Redis Url *(e.g `127.0.0.1`)*
- **REDIS_PORT** : Redis Port *(e.g `6379`)*
{.grid-list}


# Docker compose
```yaml
version: "3"
services:
  teamlock:
    image: raznak/teamlock:0.2
    ports:
      - 8000:8000
    environment:
      APP_URL: https://demo.teamlock.io
      DEBUG: "false"
      MONGO_HOST: mongodb://mongo:27017
      MONGO_DATABASE: teamlock
      # MONGO_USER: teamlock
      # MONGO_PASSWORD: teamlock
      # MONGO_AUTHSOURCE: teamlock
      REDIS_HOST: redis
      REDIS_PORT: 6379
      SMTP_AUTH: "false"
      SMTP_HOST: smtp.gmail.com
      SMTP_PORT: 587
      SMTP_SSL: "true"
      SMTP_EMAIL: email@gmail.com
      SMTP_PASSWORD: PASSWORD
      SECRET_KEY: AREALYSTRONGSECRETKEY
    volumes:
      - /var/log/teamlock:/var/log/teamlock
    depends_on:
      - redis
      - mongo

  mongo:
    image: mongo:5.0.8
    restart: always
    volumes:
      - mongodata:/data/db

  redis:
    image: redis
    restart: always
    volumes:
      - redis_data:/data

volumes:
  mongodata:
    driver: local
  redis_data:
    driver: local
```

Update the environment variables accordingly to your infrastructure then launch the stack:
```bash
docker-compose up -d
```

After, verify that the stack is successfully launched

```bash
docker ps

CONTAINER ID   IMAGE                   COMMAND                  CREATED          STATUS          PORTS                    NAMES
9c1260406322   raznak/teamlockv2:0.1   "python main.py"         50 seconds ago   Up 49 seconds   0.0.0.0:8000->8000/tcp   teamlock_teamlock_1
93b06f10ead9   mongo:5.0.8             "docker-entrypoint.s…"   50 seconds ago   Up 50 seconds   27017/tcp                teamlock_mongo_1
2916ddc7f1d5   redis                   "docker-entrypoint.s…"   50 seconds ago   Up 50 seconds   6379/tcp                 teamlock_redis_1
```

# Next
- [Configuration *Instruction to Configure Teamlock.*](/config/index)
{.links-list}
