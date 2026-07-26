# Use Node.js 18 Alpine image
FROM node:18-alpine

# Set working directory
WORKDIR /app

# Copy package files
COPY package*.json ./

# Install dependencies using package-lock.json
RUN npm ci

# Copy application source code
COPY . .

# Build the React application
RUN npm run build

# Install serve package
RUN npm install -g serve

# Expose application port
EXPOSE 3000

# Start the application
CMD ["serve", "-s", "build", "-l", "3000"]
