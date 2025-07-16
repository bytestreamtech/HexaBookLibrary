# Use the official .NET 8 SDK image for build
FROM mcr.microsoft.com/dotnet/sdk:8.0 AS build
WORKDIR /src
COPY . .
# Restore dependencies
RUN dotnet restore BookApi.csproj
# Build the project
RUN dotnet build BookApi.csproj -c Release --no-restore
# Publish the project
RUN dotnet publish BookApi.csproj -c Release -o /app/publish --no-build

# Use the official ASP.NET Core runtime image for runtime
FROM mcr.microsoft.com/dotnet/aspnet:8.0 AS runtime
WORKDIR /app
COPY --from=build /app/publish .
EXPOSE 8080
ENTRYPOINT ["dotnet", "BookApi.dll"]
