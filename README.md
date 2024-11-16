# Hosting a Website with Docker #
This project demonstrates how to containerize and host a static website using Docker. The website will be served by an Nginx web server inside a Docker container, making it portable and deployable anywhere Docker is supported.

# Features #
Lightweight: Uses the nginx:alpine image for efficiency.
Portability: Runs seamlessly on any Docker-supported platform, including cloud providers like AWS and Azure.
Ease of Deployment: With just a few commands, deploy your site anywhere.
Prerequisites
Ensure the following are installed:

# prerequisites #
Docker: Install Docker 

Git: Install Git

Step-by-Step Guide 

1. Clone Your Project Repository
Download your website's project files using Git:

bash
Copy code

     git clone https://github.com/itz-jadhav/Docker-sample-project.git

cd your-repository

# Create the Dockerfile #
The Dockerfile defines how the container is built. Create a Dockerfile in the project directory:

For Linux/Mac:

    nano Dockerfile

dockerfile:

save and exit :

    ctrl + x then y to confirm


the following content into the Dockerfile:


Use the official Nginx image from Docker Hub as a base image
FROM nginx:alpine


 
 Expose port 80 to allow web traffic
 
EXPOSE 8080

Save and close the file.

# Build the Docker Image #
   
Run the following command to build your Docker image, naming it my-static-site:


     docker build -t my-static-site .

# Run the Docker Container #
Start a container to serve your website:

onces the images is build,you run the container to server the website. the following command will run the conatiner

    docker run -d -p 8080:80


# Access Your Website #

onces the conatainer is running, you can access your website locally by navigating to:

      http://localhost:8080 in your browser. 
      
 If running on a cloud instance (e.g., AWS EC2):
 
Replace localhost with your instance's public IP address:

      http://<your-ec2-public-ip>:8080
      
# Additional Features #
To improve or expand the project:

Add an SSL certificate for HTTPS using tools like Let's Encrypt.

Create a .dockerignore file to exclude unnecessary files (e.g., .git, .env)
