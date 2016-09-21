# Docker: CouchDB container
    docker pull couchdb
    docker run -p 5984:5984 --name CouchDB -d couchdb

    docker stop CouchDB

    docker start CouchDB

As long as the container is not delete, all the database are kept

*   [https://hub.docker.com/_/couchdb/](Docker Hub)
*   [https://docs.docker.com/userguide/dockervolumes/#adding-a-data-volume](Persistant data): For persistant data when deleteing contrainer
