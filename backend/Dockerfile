# Use the official Rust image as the base image
FROM rust:1.57 AS builder

# Set the working directory
WORKDIR /usr/src/backend

# Copy the Cargo.toml and Cargo.lock files
COPY Cargo.toml Cargo.lock ./

# Create a dummy source file to build dependencies
RUN mkdir -p src && \
    echo "fn main() {}" > src/main.rs

# Build the dependencies
RUN cargo build --release

# Remove the dummy source file and copy the actual source code
RUN rm -f src/main.rs
COPY src src

# Build the release version of the backend
RUN cargo build --release

# Create a new stage with a minimal image for deployment
FROM debian:buster-slim

# Install necessary runtime dependencies
RUN apt-get update && \
    apt-get install -y libpq-dev ca-certificates && \
    rm -rf /var/lib/apt/lists/*

# Copy the binary from the builder stage
COPY --from=builder /usr/src/backend/target/release/web_app /usr/local/bin/web_app

# Set the command to run the backend
CMD ["web_app"]
