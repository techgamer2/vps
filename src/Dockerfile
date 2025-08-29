# Base Ubuntu
FROM ubuntu:22.04

# Set environment variables to avoid interactive prompts
ENV DEBIAN_FRONTEND=noninteractive

# Install packages including tmate
RUN apt-get update && \
    apt-get install -y \
    tmate \
    curl \
    git \
    vim \
    python3 \
    python3-pip && \
    rm -rf /var/lib/apt/lists/*

# Run as root (sudo is restricted in containers)
USER root

# Set working directory
WORKDIR /root

# Start tmate automatically
CMD ["tmate", "-F"]
