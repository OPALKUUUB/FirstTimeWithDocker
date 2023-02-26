# First Time with Docker

Docker is a powerful tool for containerization and deploying applications. This README.md will guide you through the process of setting up and using Docker.

## Prerequisites

Before you begin, you will need to install __Docker__ on your machine. Visit the [official Docker website](https://www.docker.com/) to download and install Docker for your operating system.

## Docker Setup

Follow the steps below to set up and use Docker:

1. Create a Dockerfile in the root directory of your project. The Dockerfile specifies the dependencies and configurations for your container. Here is an example Dockerfile for a Node.js application:
```Dockerfile
# Use an official Node.js runtime as a parent image
FROM node:14-alpine

# Set the working directory to /app
WORKDIR /app

# Copy package.json and package-lock.json to the working directory
COPY package*.json ./

# Install app dependencies
RUN npm install

# Copy the rest of the application files to the working directory
COPY . .

# Expose port 3000 for the application
EXPOSE 3000

# Run the application
CMD ["npm", "start"]
```

2. Build the Docker image by running the following command in the same directory as the Dockerfile:
```ps
docker build -t my-node-app .
```
This will create a new Docker image named "my-node-app" based on the Dockerfile in the current directory.

3. Run the Docker container by using the following command:
```ps
docker run -p 3000:3000 my-node-app
```
This will start a new container based on the "my-node-app" image and map port 3000 in the container to port 3000 on your host machine.

4. To see the running containers, use the following command:
```ps
docker ps
```
This will display a list of all running containers.

5. To stop the container, use the following command:
```ps
docker stop [container-name or container-id]
```
This will stop the specified container

## Conclusion

You now have a basic understanding of how to set up and use Docker for containerization and deployment. For more information, visit the [offcial Docker documentation](https://docs.docker.com/).