# Docker-Django
A base [Docker](https://www.docker.com/) image which utilizes a separate
 container for Django's web environment, the postgreSQL database, the
 rabbitMQ task scheduler, and each of the celery workers.
The postgreSQL database is an external container to the project which
allows for the database to persist between running docker instances.

## Requirements
- [Docker](https://www.docker.com/)
- [Docker-Compose](http://docs.docker.com/compose/install/)

### Techs used
- Python 3.6
- Django
- PostgreSQL
- Celery
- Rabbit MQ

## Instructions
Clone the repository onto your machine
``` bash
git clone https://github.com/OriginalMidas/Docker-Django.git
```
Using *build* install the requirements and preform the admin work specified within Dockerfile
``` bash
docker-compose build
```
At this point you may run into the issue of Docker not being able to see the required drives on your machine. Follow the information here:
- https://stackoverflow.com/a/43527876
- https://blog.olandese.nl/2017/05/03/solve-docker-for-windows-error-a-firewall-is-blocking-file-sharing-between-windows-and-the-containers/

Once past this, you can turn on all of the docker containers at once using
``` bash
docker-compose up
```
Other useful CLI commands
``` bash
# Stop all docker containers currently running without removing them
docker-compose stop
# Start docker containers for a service
docker-compose start [SERVICE_NAME]
# View all currently running docker containers
docker-compose ps
docker ps
# Run docker service in headless mode so you can perform other operations on the command line
docker-compose up -d
```