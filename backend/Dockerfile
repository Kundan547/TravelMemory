# Use Node.js base image
FROM node:18

# Create app directory
WORKDIR /app

# Copy package files and install dependencies
COPY package*.json ./
RUN npm install

# Copy the rest of the application code
COPY . .

# Expose the backend port
EXPOSE 5000

# Start the server
CMD ["node", "index.js"]
