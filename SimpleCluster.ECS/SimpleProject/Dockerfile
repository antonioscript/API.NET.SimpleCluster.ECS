# Etapa 1: build
FROM mcr.microsoft.com/dotnet/sdk:8.0 AS build
WORKDIR /app

# Copia os arquivos de projeto e restaura depend�ncias
COPY *.csproj ./
RUN dotnet restore

# Copia o restante do c�digo e publica
COPY . ./
RUN dotnet publish -c Release -o out

# Etapa 2: runtime
FROM mcr.microsoft.com/dotnet/aspnet:8.0 AS runtime
WORKDIR /app
COPY --from=build /app/out ./

# Exp�e a porta usada pela aplica��o
EXPOSE 8080

#ENV ASPNETCORE_URLS=http://+:8080

# Define o comando de inicializa��o
ENTRYPOINT ["dotnet", "SimpleProject.dll"]
