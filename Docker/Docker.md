# Docker Cheatsheet

Run container:
    docker run -p 5984:5984 --name MyContainer -d conainer_to_be_run
-p: map port, --name: name of the container, -d: run as deamon

Start a stopped container
    docker start MyContainer

list running containers
    docker ps

Shell in running container
    docker exec -it 6e796a466e53 bash

## Multiple containers setup
Need a config file describing the containers and their interactions.

Start container dicsconnected from the shell
    docker-compose up -d

Stop and delete containers
        docker-compose stop
        docker-compose rm
