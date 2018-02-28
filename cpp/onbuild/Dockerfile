FROM debian:testing

RUN mkdir -p /usr/src/client \
    && apt-get update \
    && apt-get install -y \
    cmake \
    g++ \
    git \
    ninja-build \
    libboost-all-dev \
    && apt-get clean \
    && git clone https://github.com/siggame/Joueur.cpp.git /usr/src/client \
    && mkdir -p /usr/src/client/build \
    && cd /usr/src/client/build \
    && cmake -GNinja .. -DCMAKE_BUILD_TYPE:STRING=Release && ninja
WORKDIR /usr/src/client/build

ONBUILD COPY . /usr/src/client
ONBUILD RUN cmake -GNinja .. -DCMAKE_BUILD_TYPE:STRING=Release && ninja
