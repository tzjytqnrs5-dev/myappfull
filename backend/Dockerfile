# Use the official Node.js 20 image as the base
FROM node:20-slim

# Create and set the working directory
WORKDIR /usr/src/app

# Copy package.json and package-lock.json to install dependencies
# We use COPY --chown=node:node to set permissions correctly
COPY --chown=node:node backend/package*.json ./

# Install application dependencies
RUN npm install

# Copy the rest of the application code
COPY --chown=node:node backend/ .

# The backend service should listen on port 8080 as required by Cloud Run/container environments
ENV PORT 8080
EXPOSE 8080

# Run the application (assuming your start script is defined in package.json)
CMD ["npm", "start"]
