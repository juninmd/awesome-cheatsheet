DOCKER MACHINE

List all Docker engines:

```sh
docker-machine ls
```

Create a Docker engine:
```sh
docker-machine create --driver virtualbox default
```

Set environment variables for Docker engine:
```sh
docker-machine env default
eval $(docker-machine env default)
```

Start a Docker engine:

```sh
docker-machine start default
```

Stop a Docker engine:

```sh
docker-machine stop default
```

Retrieve IP address for running Docker engine:

```sh
docker-machine ip default
```

DOCKER IMAGES

List Docker images:

```sh
docker images
```

Remove Docker image:

```sh
docker rmi <image_id>
docker image rm <image_id>
```

Create Docker image (requirement: Dockerfile):
```sh
docker build -t <dockerhub_username>/<custom_docker_image_name> .
```

DOCKER CONTAINERS

List Docker containers:
```sh
docker ps
docker container ls -a
```

Stop and remove Docker container:
```sh
docker stop <container_id>
docker rm <container_id>
```

Remove all stopped Docker containers:
```sh
docker container prune

Delete all stopped containers:

```sh
docker rm $(docker ps -a -q)
```

Create Docker container (requirement: Docker image):
```sh
docker run --name <custom_container_name> -p <new_port>:<defined_port> -d <dockerhub_username>/<custom_docker_image_name>
```

DOCKER COMPOSE

If development, build, run and keep running (e.g. service_id equals dev):
```sh
docker-compose build <service_id>
docker-compose up <service_id>
```

If testing, build and run once (e.g. service_id equals test):
```sh
docker-compose build <service_id>
docker-compose run --rm <service_id>
```
Credits: <https://dev.to/ibmdeveloper/docker-command-cheatsheet-1pe8>