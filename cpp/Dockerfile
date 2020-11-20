FROM debian:testing

WORKDIR /client
COPY . .
RUN apt-get update \
    && apt-get install -y \
    cmake \
    g++ \
    git \
    ninja-build \
    libboost-all-dev \
    && apt-get clean \
    && mkdir build \
    && cd build \
    && cmake -GNinja .. -DCMAKE_BUILD_TYPE:STRING=Release && ninja

ENTRYPOINT ["./build/cpp-client"]
