# Docker

- [Docker](#docker)
  - [Super summary:](#super-summary)
  - [For installation:](#for-installation)
    - [For setup docker at 1st time:](#for-setup-docker-at-1st-time)
  - [For general use:](#for-general-use)
  - [For build and manage images files:](#for-build-and-manage-images-files)
  - [Full cleanup (*my preference*):](#full-cleanup-my-preference)
    - [For cleanup:](#for-cleanup)
    - [Others for cleanup:](#others-for-cleanup)
  - [For registry (Docker Hub):](#for-registry-docker-hub)
  - [Others for registry:](#others-for-registry)
  - [For logs:](#for-logs)
  - [For volume:](#for-volume)
  - [For docker compose:](#for-docker-compose)
  - [For network:](#for-network)
  - [For bind mount:](#for-bind-mount)

## Super summary:
```
sudo docker build -f <dockerfile> -t <image_name> .
docker-compose -f <docker-compose-file> up --build
docker exec -it <container_name> /bin/bash
```

## For installation:
```
sudo apt-get update
sudo apt-get install docker.io docker-compose -y
sudo service docker start
```

### For setup docker at 1st time:
```
sudo usermod -aG docker $USER
newgrp docker
```

## For general use:
```
docker pull <REPO>:<TAG>
docker images
docker image ls
docker ps -a
docker run --rm -it --net=<NETWORK> --name <CONTAINER_NAME> <REPO>:<TAG> /bin/bash
docker run --rm -d --net=<NETWORK> --name <CONTAINER_NAME> <REPO>:<TAG>
```

## For build and manage images files:
```
docker build -f <DOCKERFILE> -t <REPO>:<TAG> .
docker build -f <DOCKERFILE> -t <REPO>:<TAG> --no-cache .
docker image save -o <PATH/TAR_FILE> <REPO>:<TAG>
docker load -i <PATH/TAR_FILE>
```

## Full cleanup (*my preference*):
```
docker kill $(docker ps -aq) &> /dev/null;
docker container prune -f
docker rmi $(docker images -q) -f
```

### For cleanup:
```
docker rmi --force <REPO>:<TAG>
docker container prune -f
docker network prune -f
docker volume prune -f
docker image prune --force --all
```

### Others for cleanup:
```
docker kill <CONTAINER_NAME> <CONTAINER_NAME>
docker kill $(docker ps -aq)
docker rm -f <CONTAINER_NAME> <CONTAINER_NAME>
docker container prune -f
```


## For registry (Docker Hub):
```
docker tag <REPO>:<TAG> <NEW_REPO>:<NEW_TAG>
docker login
docker logout
docker push <YOUR_ID/REPO>:<TAG>
```

## Others for registry:
```
docker commit <NAME> <NEW_REPO>:<NEW_TAG>
docker container cp <TAG>:<SRC_PATH> <DEST_PATH>
docker cp <SRC_PATH> <TAG>:<DEST_PATH>
```

## For logs:
```
docker logs [--follow] <CONTAINER_NAME> [since #<SECONDS>] [--tail #<LINES>]
docker exec -it <CONTAINER_NAME> /bin/bash
docker ps -a --format "table {{.ID}}\t{{.Names}}" [--filtered "exited=0"]
docker stats <CONTAINER_NAME>
```

## For volume:
```
docker volume create <VOLUME_NAME>
docker volume ls
docker volume rm <VOLUME_NAME>
docker inspect <VOLUME_NAME>
```

## For docker compose:
```
docker compose build [-f <COMPOSE_FILE>] [--no-cache]
docker compose up [-d] [-f <COMPOSE_FILE>]
docker compose down [-v] [-f <COMPOSE_FILE>]
docker compose exec <SERVICE_NAME> /bin/bash
docker compose logs [--follow] <SERVICE_NAME> [since #<SECONDS>] [--tail #<LINES>]
```

## For network:
```
docker exec <CONTAINER_NAME> ping <HOST_NAME> [-c #<COUNT>]
docker network create <NETWORK_NAME>
docker network ls
docker network rm <NETWORK_NAME>
docker network inspect <NETWORK_NAME> | grep -i name
docker network connect <NETWORK_NAME> <CONTAINER_NAME>
docker network disconnect <NETWORK_NAME> <CONTAINER_NAME>
```

## For bind mount:
```
docker run --rm -it --net=host -e DISPLAY=$DISPLAY -v /tmp/.X11-unix:/tmp/.X11-unix --volume "${pwd}/<RELATIVE_PATH>:<MOUNT_PATH>":rw <REPO>:<TAG> /bin/bash
```

