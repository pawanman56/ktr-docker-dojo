# Stage 1: Build stage
FROM --platform=linux/x86_64 gradle:6.0.1-jdk8 as build

# Set working directory
WORKDIR /app

# Copy project files
COPY . .

# Compile Java code and create runnable distribution
RUN gradle installDist

# Stage 2: Application container
FROM alpine

# Install Java
RUN apk --no-cache add openjdk8-jre

# Copy compiled application artifacts
COPY --from=build /app/build/install/search .

# Start service
ENTRYPOINT ["./bin/search"]
