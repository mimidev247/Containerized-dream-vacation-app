# --- Stage 1: Build the React Application ---
FROM node:18-alpine AS builder

WORKDIR /app

# Copy package files and install dependencies
COPY package*.json ./
RUN npm install

# Copy the rest of the frontend source code
COPY . .

# ADD THIS LINE RIGHT HERE 👇
ENV NODE_OPTIONS=--openssl-legacy-provider 

# Build the app for production (generates the build or dist folder)
RUN npm run build

# --- Stage 2: Serve the App with Nginx ---
FROM nginx:alpine

# Copy the static build files from Stage 1 into Nginx's default public directory
# Note: If your React app uses Vite, change "build" to "dist"
COPY --from=builder /app/build /usr/share/nginx/html

# Expose port 80 for web traffic
EXPOSE 80

# Start Nginx
CMD ["nginx", "-g", "daemon off;"]
