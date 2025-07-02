# Build Stage
FROM node:18 AS build

# Set working directory
WORKDIR /app

# Copy package files
COPY package.json package-lock.json ./

# Install dependencies
RUN npm install

# Copy the rest of the frontend source code
COPY . .

# Build the frontend
RUN npm run build

# Production Stage using Nginx
FROM nginx:alpine

# Copy build output to Nginx HTML folder
COPY --from=build /app/dist /usr/share/nginx/html

# Copy custom Nginx config if needed (optional)
# COPY nginx.conf /etc/nginx/nginx.conf

# Expose port for frontend
EXPOSE 5173

# Start Nginx
CMD ["nginx", "-g", "daemon off;"]
