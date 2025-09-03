# ============================
# Frontend (React + Vite
# ============================

# ---------- Build Stage ----------
FROM node:22-alpine AS build

WORKDIR /app

# Install deps
COPY package*.json ./
RUN npm install

# Copy source
COPY . .

# Build the production bundle
RUN npm run build

# ---------- Serve Stage ----------
FROM nginx:alpine AS production

# Copy build output to nginx html dir
COPY --from=build /app/dist /usr/share/nginx/html

# Expose port 80 (nginx default)
EXPOSE 80

# Run nginx
CMD ["nginx", "-g", "daemon off;"]