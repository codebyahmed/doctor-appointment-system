# Use the official Node.js slim image as the base image
FROM node:14-slim

# Set the working directory in the container
WORKDIR /app

# Set environment variables
ENV APPOINTMENTS_SERVICE_URL appointments:7070
ENV DOCTORS_SERVICE_URL doctors:9090

# Copy package.json and package-lock.json to install dependencies
COPY package*.json /app/

# Install dependencies
RUN npm install

# Copy the rest of the application code
COPY . /app/

# Expose the port on which the Node.js app will run
EXPOSE 3000

# Define the command to run the Node.js application within the container
CMD ["node", "app.js"]
