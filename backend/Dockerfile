# Stage 1: Build
FROM mcr.microsoft.com/dotnet/sdk:6.0 AS build
WORKDIR /app

# Copy project files and restore dependencies
COPY *.csproj ./
RUN dotnet restore

# Copy all source files and build the application
COPY . ./
RUN dotnet publish -c Release -o /app/publish

# Stage 2: Runtime (Smaller Final Image)
FROM mcr.microsoft.com/dotnet/aspnet:6.0 AS runtime
WORKDIR /app

# Copy the published app from the build stage
COPY --from=build /app/publish .

# Expose port 5214
EXPOSE 5214

# Define the entry point for the application
CMD ["dotnet", "backend.dll", "--urls", "http://0.0.0.0:5214"]

