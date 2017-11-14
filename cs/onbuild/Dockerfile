FROM microsoft/dotnet:sdk

RUN mkdir -p /usr/src/client
WORKDIR /usr/src/client

ONBUILD COPY nuget.config .
ONBUILD COPY Joueur.cs.csproj .
ONBUILD RUN dotnet restore

ONBUILD COPY . .
ONBUILD RUN dotnet publish -r debian-x64 -c release -o build