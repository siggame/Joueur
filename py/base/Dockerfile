FROM python:alpine

RUN addgroup -S siggame && adduser -S -G siggame siggame \
    && mkdir /client \
    && apk add --no-cache tini
WORKDIR /client

ENTRYPOINT ["/sbin/tini", "--", "python", "-u", "main.py"]
