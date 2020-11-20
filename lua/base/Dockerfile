FROM debian:buster-slim

ENV TINI_VERSION v0.17.0
ADD https://github.com/krallin/tini/releases/download/${TINI_VERSION}/tini /tini
RUN groupadd -r siggame && useradd -r -g siggame siggame \
    && apt-get update \
    && apt-get install -y lua lua-socket luajit \
    && mkdir /client && chown -R siggame:siggame /client \
    && chmod +x /tini
WORKDIR /client

ENTRYPOINT ["/tini", "--", "/usr/bin/luajit", "main.lua"]
