# Use the official Rust image as a parent image
FROM mcr.microsoft.com/devcontainers/rust:0-1-bullseye

RUN apt-get update

RUN apt-get install -y clang \
    cmake \
    libssl-dev \
    pkg-config \
    && apt-get clean && rm -rf /var/lib/apt/lists/*
   
# Set the working directory
WORKDIR /workspace

# Copy the current directory contents into the container at /workspace
COPY . /workspace

# Install any additional dependencies if needed
# RUN apt-get update && apt-get install -y <package-name>

# Build the Rust project
RUN cargo build

# Expose the port the app runs on
EXPOSE 8080

# Run the application
CMD ["cargo", "run"]