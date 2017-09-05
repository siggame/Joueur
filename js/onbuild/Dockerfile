FROM node:8.4.0

RUN mkdir -p /usr/src/client
WORKDIR /usr/src/client

ONBUILD ARG NODE_ENV
ONBUILD ENV NODE_ENV $NODE_ENV
ONBUILD COPY package.json /usr/src/client/
ONBUILD RUN npm install && npm cache clean --force

ONBUILD COPY . /usr/src/client
