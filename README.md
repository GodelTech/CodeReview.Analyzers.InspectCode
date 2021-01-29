docker build -t diamonddragon/resharper .
docker run -v "/d/temp:/src" -v "/d/temp2:/artifacts" --env SOLUTION_FILE_PATH=/src/ReviewItEasy.Analyzer.sln -it --rm diamonddragon/resharper