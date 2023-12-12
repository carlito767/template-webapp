FROM node:20.10.0-buster

# Args
ARG PNPM_VERSION=8.12.0

# Envs
ENV PNPM_VERSION=${PNPM_VERSION}
ENV PNPM_HOME=/usr/local/bin

# Set working directory
WORKDIR /workspace

# Copy configuration files
COPY .npmrc package.json pnpm-lock.yaml ./

# Update npm
RUN npm i -g npm@latest && \
  # Install pnpm
  npm install -g pnpm@$PNPM_VERSION && \
  # Configure pnpm store
  pnpm config set store-dir .pnpm-store && \
  # Install dependencies
  pnpm install --frozen-lockfile

# Copy project files
COPY . ./
