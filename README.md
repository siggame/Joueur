# Joueur

Base docker images for each client type

## Example

```bash
FROM siggame/joueur:<language>-onbuild as build

FROM alpine:latest

COPY --from=build /usr/src/client/<build artifact> /client/
WORKDIR /client

ENTRYPOINT ["arenaRun", "${GAME_NAME}"]
```

This allows for and image to be run using `docker run <image_name>:<tag>` with the `GAME_NAME` already configured.
