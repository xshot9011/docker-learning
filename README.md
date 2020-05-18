# docker-learning

## Installation
[install] (https://www.docker.com/get-started)
note: install as linux container

## create container 

create DockerFild, configuration {how container behave, what's inside, what it does when startup}
1. specify a base image
2. run commands to install program
3. specific a command to run on container startup

```bash
docker buid [path or . if in current directory] 
# got image
docker run [image's id]
```

### tag the image

```bash
docker buid -t [your docker id]/[project name]:[version] [path or . if in current directory]
```

note: can leave version blank

## run container

```bash
docker run [image] [override command]
```
create the container and run the default command form image

### container port mapping

container has it own isolate set of network port{ex. 8000 8001 8002}
computer has it own network port too, so no incoming packages coming to localhost will redirect to the container
container can go to outside world, but the 0outside world (incoming packet) not found the container

```bash
docker run -p [incoming port request]:[port inside the container] [image's id]
```

### specifying working directory

```bash
WORKDIR [path ex(/usr/app/)]
```
note: put it in DockerFile

to specific the start working directory, every command will start here

### create the container

```bash
docker create [image]
```

to create the container after running this command container's id will be given

### start and restart

```bash
docker start [-a] [container's id(may be exited status container)]
```
if a not specific, it won't show up anything above container's id
-a command make docker to watch for output for the container and print it out to terminal

note: you cannot overide the exist startup command

```bash
docker run [option] [image] [command]
```

execute the startup command and show you all the log with all the information coming out the container (opposite of docker start)

### docker volume (folder mapping)

```bash
docker run -p[port outside]:[port inside] -v [folder inside container] -v [folder outside directory]:[folder inside container] [image id]
```

first v:
we ref to node_models on local machine but we already delete it
notice: no ":" sign ==> map something outside and inside
so no ":" mean we want use this folder inside the container dont map it up to anything

second v:
$(pwd) = get the present working directory 
:/app = and map it to /app folder in container

noet: depend on folder and work

ex. docker run -p[port outside]:[port inside] -v /app/node_modules -v $(pwd):/app [image id]

## stop the container

```bash
docker stop [container's id]
```
send terminate signal >> clean up something inside

```bash
docker kill [container's id]
```
send kill signal >> shut the container down nowwww

## muliple local container

2 optino > docker cli's network feature (not recommended)
         > docker compose (recommended)

### start multiple containers

```bash
docker-compose up
# equal
docker run [image]
```

```bash
docker-compose up --build
# equal
docker build . 
docker run [image]
```

to startup container again and try to rebuild it

### stop multiple containers

notice: docker-compose up >> opposite is down 

```bash
docker-compose down
```

### get container status

```bash
# in that directory
docker-compose ps
```

find all running containers on your local machine that belong espescially to this docker-compose file

## read log

```bash
docker logs [container's id]
```
note: not rerunning or restarting the container

## remove exited container

```bash
docker system prune
```

read the waring before say yes

## listing container

```bash
docker ps [--all]
```

## running the second command in running container

### normal run

```bash
docker exec -it [container's id] [command]
```
-i > allow to  provide input directly to the container, unless use, run command and quickly exit
-t nice output format

### get the shell inside the container

to run the second process

```bash
docker exec -it [container's id] sh
```
open the shell
note: type 'exit' to exit the shell

## full doc
[doc](https://docs.docker.com/engine/reference/commandline/docker/)