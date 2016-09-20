# Docker Cheatsheet

## Start container dicsconnected from the shell
    docker-compose up -d

## Shell in running container
    docker exec -it 6e796a466e53 bash

### list running containers
    docker ps

### Start a set of containers dicsconnected from the shell
    docker-compose up -d

## Stop and delete containers
    docker-compose stop
    docker-compose rm
