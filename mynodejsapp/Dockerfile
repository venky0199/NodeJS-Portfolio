# Use an official Node.js runtime as a parent image.
# Using an Alpine-based image (e.g., node:20-alpine) is recommended for smaller image sizes.
FROM node:20-alpine

# Set the working directory inside the container.
WORKDIR /usr/src/app

# Copy package.json and package-lock.json (if present) to the working directory.
# This allows npm install to leverage Docker's layer caching, speeding up builds if dependencies don't change.
COPY package*.json ./

# Install application dependencies.
RUN npm install

# Copy the rest of the application source code to the container.
COPY . .

# Expose the port your Node.js application listens on.
# Replace 3000 with the actual port your application uses.
EXPOSE 3000

# Define the command to run your application when the container starts.
# Replace 'npm start' with the appropriate command for your application (e.g., 'node server.js').
CMD [ "node", "server.js" ]
