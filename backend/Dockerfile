# Use official Node.js image
FROM node:14

# Create and change to the app directory
WORKDIR /app

# Install app dependencies
COPY package*.json ./
RUN npm install

# Bundle app source
COPY . .

# Expose port and start the app
EXPOSE 3000
CMD ["node", "server.js"]
