FROM microsoft/dotnet-nightly:2.1-sdk

RUN mkdir -p /usr/src/client \
    && cd /usr/src \
    && git clone https://github.com/siggame/Joueur.cs.git assets \
    && mkdir -p client/build \
    && cd assets \
    && cp nuget.config Joueur.cs.sln Joueur.cs.csproj ../client \
    && cd ../client \
    && dotnet restore
WORKDIR /usr/src/client

ONBUILD COPY nuget.config .
ONBUILD COPY Joueur.cs.sln .
ONBUILD COPY Joueur.cs.csproj .
ONBUILD RUN dotnet restore

ONBUILD COPY . .
ONBUILD RUN dotnet publish -r linux-x64 -c Release -o build
