# Stage 1: Build React App
FROM node:18 as builder

# Set working directory
WORKDIR /app

# Install dependencies and build the app
COPY package*.json ./
RUN npm install

COPY . .
RUN npm run build

# Stage 2: Serve with Nginx
FROM nginx:alpine

# Copy build output to Nginx public directory
COPY --from=builder /app/build /usr/share/nginx/html

# Copy custom nginx config if needed (optional)
# COPY nginx.conf /etc/nginx/nginx.conf

# Expose frontend port
EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]
