FROM mcr.microsoft.com/dotnet/sdk:7.0 AS build
WORKDIR /source
COPY . .
RUN dotnet restore "KubernetesDotnet.csproj" --disable-parallel
RUN dotnet publish "KubernetesDotnet.csproj" -c release -o /app --no-restore

FROM mcr.microsoft.com/dotnet/aspnet:7.0
WORKDIR /app
COPY --from=build /app ./

ENV ASPNETCORE_HTTP_PORT=https://+:5001 
ENV ASPNETCORE_URLS=http://+:5000 
EXPOSE 5000

ENTRYPOINT [ "dotnet", "KubernetesDotnet.dll"]

# docker build sholiveira/k8s-dotnet .
# docker push sholiveira/k8s-dotnet