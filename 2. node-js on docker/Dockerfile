# spcific base image
# # # FROM alpine >> {the first error}
# alpine is very small, not much program are installed
# 2 option = {find dif base image(contain node and npm), attemp to install node and npm}
# find it on docker hub >> https://hub.docker.com/search?q=node&type=image
# FROM [image]:[tag]
FROM node:alpine

WORKDIR /usr/app

# install some dependencies
# # # RUN npm install
# error "no such file or directory, open '/package.json"
# because in the it is the diff part of hardware secment
# use COPY [local(relatively)] [inside container]
COPY ./package.json ./
RUN npm install
# install new depencies all the time we rebuild the image
COPY ./ ./
# minimizing cahe busting and rebuild

# Default command
CMD ["npm", "start"]

# you need to do port mapping for making it work