# docker compose

running multiple docker in local

## concept 

inside the container that we are going to create, there are 2 containers or more which create from docker image

tell docker I want to create 2 container, 1 container call "redis-server" and another call "nodejs-app" 

after makeing 2 container I want you to map some port from the containers to the local machine so we can access evrything inside of it 

## how connection create

if you are use docker compose, the containers created will be in the same network. Then, no need to open port between them

in index.js file host: 'name of service in yml file'

we can connect to it byrefering to it's name {redis-server}

index.js try to find what is this '{service}' name. 
When send the request out the app searchingfor {service} name, docker will sense it that someone try to reach {service}
and say 'that's me !!'
