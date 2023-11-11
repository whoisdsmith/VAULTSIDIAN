# Docker-commands

## Docker Build & Run ![Docker](https://img.shields.io/badge/Docker-Build-blue?style=for-the-badge)

- Create image using this directory’s Dockerfile

``` docker build -t image-name . ```

- Run “image-name” mapping port 8080 to 80

``` docker run -p 8080:80 image-name ```

- Run “image-name” mapping port 8080 to 80, but in detached mode

``` docker run -d -p 8080:80 image-name ```

- See a list of all running containers

``` docker ps ```

- Gracefully stop the specified container

``` docker stop <hash> ```

- See a list of all containers, even the ones not running

``` docker ps -a ```

- Force shutdown of the specified container

``` docker kill <hash> ```

- Remove the specified container from this machine

 ``` docker rm <hash> ```

- Remove all containers from this machine

``` docker rm $(docker ps -a -q) ```

- Show all images on this machine

``` docker images -a ```

- LEGACY: Remove the specified image from this machine

``` docker rmi <imagename> ```

- LEGACY:Remove all images from this machine

``` docker rmi $(docker images -q) ```

- LEGACY: Remove all images with dependencies

``` docker images -q | xargs docker rmi –f ```

- Log in this CLI session using your Docker credentials

``` docker login ```

- Tag <image> for upload to registry

``` docker tag <image> username/repository:tag ```

- Upload tagged image to registry

``` docker push username/repository:tag ```

- Run image from a registry

``` docker run username/repository:tag ```

- List Docker volume

``` docker volume ls ```

- List Docker Network

``` docker network ls ```

- Access an already running container and perform operations inside it

``` docker exec -it <containerId> bash ```

*********************************************

## Docker Compose ![Docker](https://img.shields.io/badge/Docker-Compose-blue?style=for-the-badge)

- Build Docker Images using Docker Compose file

``` docker-compose build ```

- Run Docker Containers

``` docker-compose up ```

- Run Docker Containers in background Mode

``` docker-compose up -d ```

- Build Images before starting Containers

``` docker-compose up --build ```

- Recreate Containers from existing images

``` docker-compose up --force-recreate ```

- Stop and Remove Containers, Volumes, Networks, and Images

``` docker-compose down ```

- List Containers

``` docker-compose ps -a ```

- Display Log output

``` docker-compose logs ```

******************************************************

## Docker Swarm ![Docker](https://img.shields.io/badge/Docker-Swarm-blue?style=for-the-badge)

- Initialize

``` docker swarm init ```

- Join Docker Cluster

```` docker swarm join --token SWMTKN-1-3pu6hszjas19xyp7ghgosyx9k8atbfcr8p2is99znpy26u2lkl-1awxwuwd3z9j1z3puu7rcgdbx <manager/worker>:2377 ```

- List Docker Nodes in Swarm Cluster

``` docker node ls ```

- List all running applications on this Docker host

``` docker stack ls ```

- Run the specified Compose file

``` docker stack deploy -c <composefile> <STACK_NAME> ```

- List the services associated with an app

``` docker stack services <appname> ```

- List the running containers associated with an app

``` docker stack ps <appname> ```

- Tear down an application

``` docker stack rm <STACK_NAME>alias dstr='docker stack rm' ```

- Docker Swarm Service list

``` docker service ls ```  
``` alias dsls='docker service ls' ```

- List the tasks of one or more services

``` docker service ps <service_name>  ```  
``` alias dsp='docker service ps' ```

- Docker Swarm Service logs

``` alias dsl='docker service logs' ```

- Remove specific docker swarm service

``` alias dsr='docker service rm' ```

- Remove unused Containers, Images, Network, etc.

``` alias sprune='docker system prune' ```

- Remove unused Volumes

``` alias vprune='docker volume prune' ```

- Create Secret

``` docker secret create <SECRET_NAME> <SECRET_PATH> ```

- Create Config

``` docker config create <CONFIG_NAME> <CONFIG_FILE_PATH> ```

## To Delete All Containers including Its Volumes Use

```docker rm -vf $(docker ps -a -q)```

## To Delete All the Images

```docker rmi -f $(docker images -a -q)```

> Remember, you should remove all the containers before removing all the images from which those containers were created.

## In case You Are Working on Windows (Powershell)

```bash
$images = docker images -a -q
foreach ($image in $images) { docker image rm $image -f }
```

## To Delete All Images

```docker rmi $(docker images -a)```

## To Delete Containers Which Are in Exited State

```docker rm $(docker ps -a -f status=exited -q)```

## To Delete Containers Which Are in Created State

```docker rm $(docker ps -a -f status=created -q)```

> NOTE: Remove all the containers then remove the images 

## Docker Run Bash Shell of Image

```docker run -it --entrypoint bash <image-name>```

## List All Docker Commands

``` docker --help ```
