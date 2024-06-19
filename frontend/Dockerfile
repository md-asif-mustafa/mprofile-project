# Use the official Node.js image as a base
FROM node:14

# Set the working directory in the container
WORKDIR /usr/src/app

# Copy package.json and package-lock.json to the working directory
COPY package*.json ./

# Install the dependencies
RUN npm install

# Copy the rest of the application code to the working directory
COPY . .

# Build the application
RUN npm run build

# Install a simple HTTP server to serve static files
RUN npm install -g serve

# Expose the port the application will run on
EXPOSE 3000

# Command to run the application
CMD ["serve", "-s", "build", "-l", "3000"]
