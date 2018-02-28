FROM node:latest

RUN mkdir -p /usr/src/client
WORKDIR /usr/src/client

ONBUILD ENV NODE_ENV production
ONBUILD COPY package.json .
ONBUILD RUN npm install && npm cache clean --force

ONBUILD COPY . /usr/src/client
