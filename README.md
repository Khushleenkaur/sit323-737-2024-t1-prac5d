Project Overview
This repository contains a simple Node.js microservice that responds with "Hello World" when accessed via HTTP. The project demonstrates how to containerize this microservice using Docker and deploy it to a Google Cloud Container Registry.

Prerequisites
Git
Node.js
Docker
Google Cloud SDK

Setup
Clone this repository and install the necessary Node.js dependencies.
git clone https://github.com/Khushleenkaur/sit323-737-2024-t1-prac5d.git

cd sit323/737-2024-t1-prac5d
npm install

Running the Application Locally
Start the application with the following command:
node app.js

Access the application at http://localhost:3000 to see the "Hello World!" message.

Containerization with Docker
Building the Docker Image
Create a Docker image by running:

docker build -t my-microservice .

Running the Docker Container Locally
Run your Docker container using:
docker run -p 3000:3000 my-microservice

Check http://localhost:3000 in your browser to see if the Dockerized app is running.

Deployment to Google Cloud Container Registry
Configure Docker with Google Cloud
Ensure you are authenticated and Docker is configured to push to your Google Cloud registry:

gcloud auth login
gcloud auth configure-docker

Tagging and Pushing the Docker Image
Tag and push the Docker image to your Google Cloud project:

docker tag my-microservice gcr.io/[YOUR-PROJECT-ID]/my-microservice:v1
docker push gcr.io/[YOUR-PROJECT-ID]/my-microservice:v1

Verifying Deployment
After deploying, pull and run the image from the Google Cloud registry to verify:
docker run -p 3000:3000 gcr.io/[YOUR-PROJECT-ID]/my-microservice:v1

Access http://localhost:3000 to ensure the microservice is running properly in the cloud.



