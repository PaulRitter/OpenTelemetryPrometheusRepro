FROM mcr.microsoft.com/dotnet/sdk:8.0 AS build

WORKDIR /source
COPY . .
RUN dotnet publish -c Release -o /app

FROM mcr.microsoft.com/dotnet/aspnet:8.0 as run

WORKDIR /app
COPY --from=build /app .

EXPOSE 8080

CMD dotnet WebMetric8.dll