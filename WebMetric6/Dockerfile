FROM mcr.microsoft.com/dotnet/sdk:6.0 AS build

WORKDIR /source
COPY . .
RUN dotnet publish -c Release -o /app

FROM mcr.microsoft.com/dotnet/aspnet:6.0 as run

WORKDIR /app
COPY --from=build /app .

EXPOSE 80

CMD dotnet WebMetric6.dll