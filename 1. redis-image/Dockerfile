# step
# 1. specify a base image
# instruction telling docker server what to do something on the image we are going to create
# specific docker image that we want to use as a base
FROM alpine  
# like install an os, starting point for {image1} creaing

# 2. run commands to install program
# to run command while we are preparing custom image
RUN apk add --update redis
# use package manager of alpine to do add....
# create the temporary container from {image1} then exec command inside the container
# then take a FS snapshot of previous container to the new temporary {image2}

RUN apk add --update gcc
# looking when second exec docker build . (second time)>> not dowload everything again
# see caching of docker in the step using old container
# run again (third time) you will see 
# caching is in series of command

# 3. specific a command to run on container's startup
# command that execute when startup an new container
CMD ["redis-server"]
# make the new temporary container using previous {image2}
# setting the primary command & primary process of the container
# tell container if you are run for real, you should run this as your primary command
# create the new {image3}
