# Etapa 1: build
FROM mcr.microsoft.com/dotnet/sdk:8.0 AS build
WORKDIR /app

# Copia os arquivos de projeto e restaura dependências
COPY *.csproj ./
RUN dotnet restore

# Copia o restante do código e publica
COPY . ./
RUN dotnet publish -c Release -o out

# Etapa 2: runtime
FROM mcr.microsoft.com/dotnet/aspnet:8.0 AS runtime
WORKDIR /app
COPY --from=build /app/out ./

# Expõe a porta usada pela aplicação
EXPOSE 8080

#ENV ASPNETCORE_URLS=http://+:8080

# Define o comando de inicialização
ENTRYPOINT ["dotnet", "SimpleProject.dll"]
