FROM microsoft/dotnet-nightly:2.1-sdk

RUN mkdir -p /usr/src/client
WORKDIR /usr/src/client

ONBUILD COPY nuget.config .
ONBUILD COPY Joueur.cs.sln .
ONBUILD COPY Joueur.cs.csproj .
ONBUILD RUN dotnet restore

ONBUILD COPY . .
ONBUILD RUN dotnet publish -r linux-x64 -c Release -o build