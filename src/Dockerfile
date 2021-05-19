FROM mcr.microsoft.com/dotnet/sdk:3.1
RUN apt-get update && apt-get install wget && wget https://packages.microsoft.com/config/ubuntu/20.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb && dpkg -i packages-microsoft-prod.deb && apt-get update && apt-get install -y dotnet-sdk-5.0 && rm packages-microsoft-prod.deb

ENV SOLUTION_FILE_PATH=""
VOLUME /artifacts
VOLUME /src

RUN mkdir /tools
WORKDIR /tools

RUN dotnet new tool-manifest
RUN dotnet tool install JetBrains.ReSharper.GlobalTools

CMD dotnet build $SOLUTION_FILE_PATH && dotnet jb inspectcode $SOLUTION_FILE_PATH -o=/artifacts/result.xml