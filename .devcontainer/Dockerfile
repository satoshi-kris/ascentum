# .devcontainer/Dockerfile
FROM rust:latest

# Install Solana CLI
RUN sh -c "$(curl -sSfL https://release.solana.com/v1.14.10/install)"

# Install Anchor CLI
RUN cargo install --git https://github.com/project-serum/anchor --tag v0.30.0 anchor-cli --locked

# Set environment variables
ENV ANCHOR_WALLET=/root/.config/solana/id.json
ENV ANCHOR_PROVIDER_URL=http://localhost:8899

WORKDIR /workspace