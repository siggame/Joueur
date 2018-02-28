FROM java:jre-alpine

RUN addgroup -S siggame && adduser -S -G siggame siggame \
    && mkdir /client
WORKDIR /client

ENTRYPOINT ["java", "-jar", "java-client.jar"]
