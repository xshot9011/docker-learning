# make it producetion grade

(start) >> development >> testing >> deployment >> (start)

using DOckerfile.dev

ิbut docker cannot find Dockerfile.dev

you need to run another command to build image

```bash
docker build -f Dockerfile.dev .
```
## making this app

note: install node is required

```bash
npm install -g create-react-app
cd [to the directody]
create-react-app [name]
```

## nodejs command

### startup deveopment server

```bash
npm run start
```

### run test associated with project

```bash
npm run test
```

### build a production version of application

```bash
npm run build
```

## updating code to docker real time

once you update code in your local machine, absolutely nothing make change in container 
in order to get the update, we are going to do straig copy
we need to adjust docker run command that we used it to run the container
called "volume"

concept::
in container base file will reference to local machine so any change we made it will update in container too

like container port mapping concept::
map the port inside the container to port outside the container
equal to
map the folder inside the container to folder outside the container

go to readme.md in root folder and find docker volume

## shortcut to your container

some kind of process need only short cut to work for ex react npm run test
after we have done live updating, we will use something call docker attach

go to roor readme.md to find more syntax

concept:
there are many processes running in the container, so when you send some command it will go to stdin of the primary process
absolutely not the process that we want, the web server is another process running on that container 

in this case:
npm make another process for "run test" >> so when outside conatiner command com it will blow to "npm" process
npm doesn't know what the heck is "your command"