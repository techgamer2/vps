# Use Ubuntu as base
FROM ubuntu:22.04

# Set environment variables to avoid interactive prompts
ENV DEBIAN_FRONTEND=noninteractive

# Update and install necessary packages
RUN apt-get update && \
    apt-get install -y \
    tmate \
    sudo \
    curl \
    git \
    vim \
    openssh-client && \
    rm -rf /var/lib/apt/lists/*

# Create a non-root user for security
RUN useradd -m dockeruser && echo "dockeruser:dockeruser" | chpasswd && adduser dockeruser sudo

# Set working directory
WORKDIR /home/dockeruser

# Switch to non-root user
USER dockeruser

# Default command: launch tmate
CMD ["tmate", "-F"]
