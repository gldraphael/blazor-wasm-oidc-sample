FROM mcr.microsoft.com/dotnet/sdk:9.0-bookworm-slim AS build-env
WORKDIR /app

COPY ./WasmApp ./WasmApp
RUN dotnet publish -c Release -r linux-x64 --self-contained -o /app/out ./WasmApp/WasmApp.csproj

FROM georgjung/nginx-brotli:mainline-bookworm AS final
WORKDIR /usr/share/nginx/html
COPY nginx.conf /etc/nginx/nginx.conf

COPY --from=build-env /app/out/wwwroot .
