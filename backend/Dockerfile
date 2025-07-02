# Use Node.js official image
FROM node:18

# Set working directory
WORKDIR /app

# Copy package files
COPY package.json package-lock.json ./

# Install dependencies
RUN npm install

# Copy the entire backend source code
COPY . .

# Expose backend port
EXPOSE 8080

# Start the backend server
CMD ["npm", "start"]
