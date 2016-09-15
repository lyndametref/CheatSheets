### list running containers
    docker ps

### Shell in running container (run a command in a running container)

    docker exec -it 6e796a466e53 bash

### Start a set of containers dicsconnected from the shell

    docker-compose up -d

### Stop and delete sets of containers

    docker-compose stop
    docker-compose rm
