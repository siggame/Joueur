FROM siggame/joueur:lua-onbuild as build

FROM siggame/joueur:lua-base

COPY --from=build --chown=siggame:siggame /usr/src/client /client
