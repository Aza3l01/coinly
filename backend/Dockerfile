# ============================
# Backend (Node + Express API)
# ============================

# Base image
FROM node:22-alpine AS base

WORKDIR /usr/src/app

# Install only package.json first (layer caching)
COPY package*.json ./

# Install dependencies
RUN npm install --production

# Copy rest of source code
COPY . .

# Expose backend port (match your server.js/app.js port)
EXPOSE 5000

# Start server
CMD ["npm", "start"]