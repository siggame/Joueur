FROM debian:testing

RUN mkdir -p /usr/src/client/build
WORKDIR /usr/src/client/build

RUN apt-get update && apt-get install -y \
    cmake \
    g++ \
    ninja-build \
    && apt-get clean

ONBUILD COPY . /usr/src/client
ONBUILD RUN cmake -GNinja .. -DCMAKE_BUILD_TYPE:STRING=RelWithDebInfo && ninja