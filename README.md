# siggame/Joueur

Base images for building joueur clients in various languages.

[![Docker Pulls](https://img.shields.io/docker/pulls/siggame/joueur.svg?style=flat-square)](https://hub.docker.com/r/siggame/Joueur/)
[![GitHub Tag](https://img.shields.io/github/tag/siggame/Joueur.svg?style=flat-square)](https://github.com/siggame/Joueur/tags)

## Table Of Contents

- [Description](#description)
- [Getting Started](#getting-started)
- [Usage](#usage)
- [Contributors](#contributors)
- [Change Log](#change-log)
- [License](#license)
- [Contributing](#contributing)

## Description

Joueur is a collection of Dockerfiles for configuring the builds of Joueur clients from different languages.
Each image has `ONBUILD` triggers so that a new image using an `<lang>-onbuild` as the base will be able to rely
on preprocessed assets to improve build times. The produced build artifacts are then made available using Docker's
multistage builds. Multistage builds allow for the resulting image to only have the necessary resources to run
a client. The structure of the build process also reduces the amount of redundant data that is generated during
builds. The images can rely on the cached layers so that when building many clients there is little cost while
keeping isolation between builds.

## Getting Started

Get [Docker](https://www.docker.com/get-docker).

## Usage

Example Joueur.cpp Dockerfile:

```Dockerfile
FROM siggame/joueur:cpp-onbuild as build

FROM debian:buster-slim

RUN mkdir /client
WORKDIR /client
COPY --from=build /usr/src/client/build/cpp-client .

ENTRYPOINT ["./cpp-client", "Saloon"]
```

## Contributors

- [Russley Shaw](https://github.com/russleyshaw)
- [user404d](https://github.com/user404d)
- [Hannah Reinbolt](https://github.com/LoneGalaxy)
- [Matthew Qualls](https://github.com/MatthewQualls)

## Change Log

View our [CHANGELOG.md](https://github.com/siggame/Joueur/blob/master/CHANGELOG.md)

## License

View our [LICENSE.md](https://github.com/siggame/colisee/blob/master/LICENSE.md)

## Contributing

View our [CONTRIBUTING.md](https://github.com/siggame/colisee/blob/master/CONTRIBUTING.md)
