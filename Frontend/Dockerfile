# frontend/Dockerfile

# Use official Node image
FROM node:18

# Set working directory
WORKDIR /app

# Copy files
COPY . .

# Install dependencies
RUN npm install

# Build the React app
RUN npm run build

# Use an NGINX image to serve static files
FROM nginx:alpine

# Copy built files to NGINX html folder
COPY --from=0 /app/build /usr/share/nginx/html

# Expose port
EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]
