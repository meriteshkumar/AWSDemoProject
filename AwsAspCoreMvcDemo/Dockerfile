FROM mcr.microsoft.com/dotnet/core/sdk:3.1 AS build
COPY . /build
WORKDIR /build
RUN dotnet publish -c Release -o /app

FROM mcr.microsoft.com/dotnet/core/aspnet:3.1 AS final
WORKDIR /app
COPY --from=build /app .
ENTRYPOINT ["dotnet", "AwsAspCoreMvcDemo.dll"]
