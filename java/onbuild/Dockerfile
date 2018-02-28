FROM maven:latest

RUN mkdir -p /usr/src/client/src/main/java /usr/src/client/target /usr/src/client/.m2 \
    && echo '<settings xmlns="http://maven.apache.org/SETTINGS/1.0.0" \
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" \
    xsi:schemaLocation="http://maven.apache.org/SETTINGS/1.0.0 \
    https://maven.apache.org/xsd/settings-1.0.0.xsd"> \
    <localRepository>/usr/src/client/.m2</localRepository></settings>' \
    | tee /usr/src/client/.m2/settings.xml \
    && git clone https://github.com/siggame/Joueur.java.git assets \
    && cp assets/pom.xml /usr/src/client \
    && cd /usr/src/client \
    && mvn -s .m2/settings.xml dependency:go-offline
WORKDIR /usr/src/client

ONBUILD COPY pom.xml /usr/src/client
ONBUILD RUN mvn -s .m2/settings.xml dependency:go-offline 

ONBUILD COPY . /usr/src/client
ONBUILD RUN mvn -s .m2/settings.xml -o compile assembly:single
