FROM mono:latest

RUN mkdir -p /usr/src/client/.nuget
WORKDIR /usr/src/client

ONBUILD COPY .nuget .nuget
ONBUILD COPY packages.config .
ONBUILD COPY Joueur.cs.sln .
ONBUILD COPY Joueur.cs.csproj .
ONBUILD COPY Joueur.cs.shfbproj .
ONBUILD RUN nuget restore Joueur.cs.sln

ONBUILD COPY . .
ONBUILD RUN msbuild /p:Configuration=Release Joueur.cs.sln