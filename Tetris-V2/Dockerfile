# Use the official Node.js 18 image as the base image
FROM node:18

# Set the working directory inside the container
WORKDIR /app

# Copy only the package.json and package-lock.json first
COPY package*.json ./

# Install compatible postcss version (to fix build errors)
RUN npm install postcss@7.0.39 --save-exact

# Install remaining project dependencies
RUN npm install

# Copy the rest of the application source code
COPY . .

# Build the React app
RUN npm run build

# Expose the port that the app will run on
EXPOSE 3000

# Start the React app
CMD [ "npm", "start" ]
