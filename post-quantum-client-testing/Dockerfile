FROM rust:1.90.0-bullseye AS build

ARG SERVICE_ACCOUNT_JSON
ENV SERVICE_ACCOUNT_JSON=${ACCESS_TOKEN}

# Install dependencies
RUN apt-get update && apt-get install -y \
    libclang-dev \
    cmake

# Set directory
WORKDIR /src

# Copy the project files and dependencies into container
COPY Cargo.toml Cargo.lock ./
COPY src ./src

# Build the executable
RUN cargo build --release
