FROM mcr.microsoft.com/dotnet/sdk:5.0 AS build-env AS build
WORKDIR /app

# Copiar csproj e restaurar dependencias
COPY *.csproj ./
RUN dotnet restore

# Build da aplicacao
COPY . ./
RUN dotnet publish -c Release -o out

# Build da imagem
FROM mcr.microsoft.com/dotnet/apsnet:5.0 AS build-env AS base
WORKDIR /app
ENTRYPOINT ["dotnet", "aspnetapp.dll"]

