FROM node:16.14.0-buster

WORKDIR /workspace

# Install project dependencies
COPY package*.json ./
RUN npm install

# Copy project files
COPY . ./
