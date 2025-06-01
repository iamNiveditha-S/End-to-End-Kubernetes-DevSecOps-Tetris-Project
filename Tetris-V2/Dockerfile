# Use official Node.js 18 image
FROM node:18

# Set working directory
WORKDIR /app

# Copy only dependency files first
COPY package*.json ./

# Install specific PostCSS v7 version before any other install
RUN npm install postcss@7.0.39 --save-exact

# Install rest of dependencies (which will use PostCSS v7 instead of latest)
RUN npm install

# Copy remaining application code
COPY . .

# Build the React app
RUN npm run build

# Expose the port
EXPOSE 3000

# Run the app
CMD ["npm", "start"]
