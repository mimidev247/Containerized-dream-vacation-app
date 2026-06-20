# Step 1: Use an official Node.js runtime as the base image
FROM node:18-alpine

# Step 2: Set the working directory inside the container
WORKDIR /app

# Step 3: Copy package.json and package-lock.json first to cache layers
COPY package*.json ./

# Step 4: Install the backend dependencies
RUN npm install

# Step 5: Copy the rest of the application code
COPY . .

# Step 6: Expose the port the backend runs on (usually 5000 or 8000 for Node apps)
EXPOSE 5000

# Step 7: Define the command to run the app
CMD ["npm", "start"]
