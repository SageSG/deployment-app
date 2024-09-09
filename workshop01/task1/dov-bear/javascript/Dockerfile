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
ENV PORT=3000 INSTANCE_NAME="javascript_local" INSTANCE_HASH="test12345"

HEALTHCHECK --interval=30s --timeout=5s --start-period=5s --retries=3 \
    CMD curl -s localhost:${PORT}/healthz || exit 1

# what are the explosed port
EXPOSE ${PORT}

ENTRYPOINT node main