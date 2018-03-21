FROM java:jre-alpine

RUN addgroup -S siggame && adduser -S -G siggame siggame \
    && mkdir /client \
    && apk add --no-cache tini
WORKDIR /client

ENTRYPOINT ["/sbin/tini", "--", "java", "-jar", "java-client.jar"]
