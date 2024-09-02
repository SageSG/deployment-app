FROM node:22
#How to build 

# create a directory /app and cd /app
WORKDIR /app

#Inside app
#Copy root src

COPY ./main.js .
COPY ./package*.json .
COPY ./public public
COPY ./views views

#Install the node modules
RUN npm ci

#Set environment variable
ENV PORT=3000
ENV INSTANCE_NAME="javascript_local"
ENV INSTANCE_HASH="test12345"

# what are the explosed port
EXPOSE ${PORT}

ENTRYPOINT node main