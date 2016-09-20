# Docker Cheatsheet
<!-- TOC depthFrom:2 depthTo:6 withLinks:1 updateOnSave:1 orderedList:0 -->

- [Start container dicsconnected from the shell](#start-container-dicsconnected-from-the-shell)
- [Shell in running container](#shell-in-running-container)
- [Stop and delete containers](#stop-and-delete-containers)

<!-- /TOC -->
## Start container dicsconnected from the shell

    docker-compose up -d

## Shell in running container

    docker exec -it 6e796a466e53 bash

## Stop and delete containers

    docker-compose stop
    docker-compose rm
