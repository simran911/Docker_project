Simple Dockerized Website
This project demonstrates how to create and deploy a simple HTML website using Docker. The website is served using an Nginx container, making it easy to run anywhere with Docker installed.

Project Structure

simple-website/
├── Dockerfile          # Dockerfile to build the Nginx image with the website
└── index.html          # HTML file for the website's homepage

Prerequisites

Docker: Make sure Docker is installed on your system. You can download it from Docker’s official website.

Getting Started
Step 1: Clone or Create the Project Directory
Create a directory for the project if it doesn’t exist:


mkdir simple-website
cd simple-website

Step 2: Create index.html
Create an HTML file named index.html with the following content:

html

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Simple Website</title>
    <style>
        body { font-family: Arial, sans-serif; text-align: center; margin-top: 50px; }
        h1 { color: #4CAF50; }
        p { color: #555; }
    </style>
</head>
<body>
    <h1>Welcome to My Simple Website</h1>
    <p>This is a basic HTML website running in a Docker container.</p>
</body>
</html>


Step 3: Create the Dockerfile
Create a file named Dockerfile in the same directory with the following content:

dockerfile

# Use an official Nginx image as the base
FROM nginx:alpine

# Copy the HTML file to the default Nginx location
COPY index.html /usr/share/nginx/html/index.html

# Expose port 80 to the outside world
EXPOSE 80

# Start Nginx when the container starts
CMD ["nginx", "-g", "daemon off;"]
Step 4: Build the Docker Image
Run the following command in the terminal to build the Docker image:


docker build -t simple-website .
Step 5: Run the Docker Container
Run the container and map it to port 8080 on your host machine:


docker run -d -p 8080:80 simple-website
Step 6: View the Website
Open your browser and go to http://localhost:8080 to see your simple website.

Additional Commands
Stop the Container:

Find the container ID with:


docker ps
Then stop it with:


docker stop <container_id>
Remove the Container:

docker rm <container_id>
Remove the Image:


docker rmi simple-website

Resources
Docker Documentation
Nginx Documentation
