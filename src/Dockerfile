FROM mcr.microsoft.com/dotnet/sdk:3.1

ENV SOLUTION_FILE_PATH=""
VOLUME /artifacts
VOLUME /src

RUN mkdir /tools
WORKDIR /tools

RUN dotnet new tool-manifest
RUN dotnet tool install JetBrains.ReSharper.GlobalTools

CMD dotnet jb inspectcode $SOLUTION_FILE_PATH -o=/artifacts/result.xml