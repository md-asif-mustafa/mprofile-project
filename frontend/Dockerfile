# Stage 1: Build the application
FROM node:14 AS BUILD_IMAGE

# Set the working directory
WORKDIR /app

# Copy package.json and package-lock.json
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of the application source code
COPY . .

# Build the application (if applicable)
RUN npm run build

# Stage 2: Run the application
FROM node:14-alpine

# Set the working directory
WORKDIR /app

# Copy the built application from the previous stage
COPY --from=BUILD_IMAGE /app .

# Expose the port the app runs on
EXPOSE 3000

# Command to run the application
CMD ["npm", "start"]
