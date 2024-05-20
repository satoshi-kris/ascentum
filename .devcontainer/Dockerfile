# .devcontainer/Dockerfile
FROM rust:latest

# Install Solana CLI
RUN curl -sSfL https://release.solana.com/v1.18.14/install | sh -s

# Add Solana CLI to PATH
ENV PATH="/root/.local/share/solana/install/active_release/bin:$PATH"

# Install Anchor CLI dependencies
RUN apt-get update && apt-get install -y \
    pkg-config \
    libssl-dev \
    build-essential \
    cmake

# Install Anchor CLI
RUN cargo install --git https://github.com/coral-xyz/anchor --tag v0.30.0 anchor-cli --locked

# Add Anchor CLI to PATH
ENV PATH="/root/.cargo/bin:$PATH"

# Set environment variables for Solana and Anchor
ENV ANCHOR_WALLET=/root/.config/solana/id.json
ENV ANCHOR_PROVIDER_URL=http://localhost:8899

# Set the working directory
WORKDIR /workspace
