FROM mcr.microsoft.com/dotnet/sdk:7.0

ENV SOLUTION_FILE_PATH=""
VOLUME /artifacts
VOLUME /src

RUN mkdir /tools
WORKDIR /tools

RUN dotnet new tool-manifest
RUN dotnet tool install JetBrains.ReSharper.GlobalTools

CMD dotnet restore $SOLUTION_FILE_PATH && dotnet jb inspectcode $SOLUTION_FILE_PATH -o=/artifacts/result.xml