FROM mcr.microsoft.com/dotnet/sdk:6.0 AS build-env
WORKDIR /APP
COPY . ./
RUN dotnet restore & dotnet publish -c Release -o out

FROM mcr.microsoft.com/dotnet/aspnet:6.0
WORKDIR /APP
COPY --from=build-env /APP/out .
ENTRYPOINT ["dotnet","DotNet.Docker.dll"]