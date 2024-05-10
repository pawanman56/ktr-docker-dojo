# Use NodeJS base image
FROM node:13-alpine

# Working directory
WORKDIR /app

# Copy artifacts
COPY . .

# Install dependencies
RUN npm install

# Expose port
EXPOSE 8080

# Start NodeJS server
CMD ["npm", "start"]
