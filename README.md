# CodeReview.Analyzers.InspectCode

NuGet: https://hub.docker.com/r/godeltech/codereview.analyzers.inspectcode

## Description

This project provides a Docker image to run [JetBrains.ReSharper.GlobalTools](https://www.nuget.org/packages/jetbrains.resharper.globaltools) for code inspection.

## Usage

### How to build the Docker Image

To build the Docker image, run the following commands:

```bash
docker build -t godeltech/codereview.analyzers.inspectcode:0.0.1 . 
```

### How to run the Docker Container

To run the Docker container, use the following command:

```bash
docker run -v "/d/temp:/src" -v "/d/temp2:/artifacts" --env SOLUTION_FILE_PATH=/src/ReviewItEasy.Analyzer.sln -it --rm godeltech/codereview.analyzers.inspectcode
```

## License

This project is licensed under the MIT License. See the LICENSE file for more details.