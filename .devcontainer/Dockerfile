# .devcontainer/Dockerfile
FROM rust:latest

# Install Solana CLI
RUN sh -c "$(curl -sSfL https://release.solana.com/v1.18.14/install)"

# Install Anchor CLI
RUN apt-get update && apt-get install -y pkg-config libssl-dev build-essential
RUN cargo install --git https://github.com/coral-xyz/anchor --tag v0.30.0 anchor-cli --locked

# Set environment variables
ENV ANCHOR_WALLET=/root/.config/solana/id.json
ENV ANCHOR_PROVIDER_URL=http://localhost:8899

# Set the working directory
WORKDIR /workspace
