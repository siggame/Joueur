FROM debian:testing

RUN mkdir -p /usr/src/client && apt-get update && apt-get install -y \
    cmake \
    g++ \
    git \
    ninja-build \
    && apt-get clean \
    && cd /usr/src \
    && git clone https://github.com/siggame/Joueur.cpp.git client \
    && mkdir -p client/build \
    && cd client/build \
    && cmake -GNinja .. -DCMAKE_BUILD_TYPE:STRING=Release && ninja
WORKDIR /usr/src/client/build

ONBUILD COPY . /usr/src/client
ONBUILD RUN cmake -GNinja .. -DCMAKE_BUILD_TYPE:STRING=Release && ninja