FROM debian:buster-slim

RUN groupadd -r siggame && useradd -r -g siggame siggame \
    && mkdir /client
WORKDIR /client

ENTRYPOINT ["./cpp-client"]
