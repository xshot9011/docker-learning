# docker-learning

## Installation
[install] (https://www.docker.com/get-started)
note: install as linux container

## run container

```bash
docker run [image] [override command]
```
create the container and run the default command form image

```bash
docker create [image]
```

to create the container after running this command container's id will be given

```bash
docker start [-a] [container's id]
```

if a not specific, it won't show up anything above container's id
-a command make docker to watch for output for the container and print it out to terminal

```bash
docker run [option] [image] [command]
```

show you all the log with all the information coming out the container (opposite of docker start)

## listing container

```bash
docker ps [--all]
```

## full doc
[doc](https://docs.docker.com/engine/reference/commandline/docker/)