FROM node:alpine

ENV NODE_ENV production
RUN addgroup -S siggame && adduser -S -G siggame siggame \
    && mkdir /client \
    && apk add --no-cache tini
WORKDIR /client

ENTRYPOINT ["/sbin/tini", "--", "node", "main.js"]
