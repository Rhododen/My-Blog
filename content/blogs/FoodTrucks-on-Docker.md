---
title: "FoodTrucks on Docker"
date: 2023-06-19T19:59:38+01:00
draft: true
author: Rhoda
tags:
image:
description:
---

As mentioned in the previous blog post, To prevent the classic "it worked in my machine" problem, Docker helps developers achieve a faster, more reproducible, and more secure development environment.

<!-- Image -->

The FoodTruck application is a web application that allows users to find food trucks near their current location. The application comprises a Flask backend server and an Elasticsearch service which is responsible for enabling our application to search for food trucks. 

A sensible approach to dividing this application would involve utilizing two containers: one to execute the Flask process and another to handle the Elasticsearch (ES) process. This arrangement allows for easy scalability of the application by adding additional containers as necessary. 

The source code for the backend server is from this github repository and we will have to build the image specifically for this container. Fortunately, there is no need for us to build an image for Elasticsearch service as an official elasticSearch image is already available.


Step 1: Create a Dockerfile
A Dockerfile is simply a text file that lists the instructions needed to build a Docker image. These commands closely resemble the commands we would execute if we were manually setting up the application on a server.


# start from base 
FROM ubuntu:18.04 

# Install dependencies

RUN apt-get -yqq update 
RUN apt-get -yqq install python3-pip python3-dev curl gnupg 
RUN curl -sL https://deb.nodesource.com/setup_10.x | bash RUN apt-get install -yq nodejs 

# copy the application code and set a working directory

ADD flask-app /opt/flask-app 
WORKDIR /opt/flask-app 

# fetch more app-specific dependencies 

RUN npm install 
RUN npm run build 
RUN pip3 install -r requirements.txt

 # expose port 
EXPOSE 5000 

# start app 

CMD [ "python3", "./app.py" ]



Let me explain the content of the file:

FROM ubuntu:18.04 : Every Dockerfile typically starts with specifying the base image and this is done with the  FROM command.  The base image (ubuntu in our case) is an existing image that closely matches your application's runtime environment and it could be an official image from Docker Hub or a custom image.


The RUN command executes the commands during the image build process. These commands can include installing packages, setting up dependencies, and performing other tasks required to prepare the container image and the -yqq flag is to ensure that package installations proceed silently without any prompts or unnecessary output.

The ADD command is used to copy files from the host system to the Docker image, while the WORKDIR command specifies the working directory within the container where subsequent commands will be executed.

We then expose the Port 5000 and this allows traffic to reach the application when the container is running.

Finally, CMD defines the command to be executed when the container is started.

Step 2: Build the Docker Image

The docker image is built with the command below.

docker build -t yourusername/food-trucks .

Make sure to run the command in the directory where the Docker file is located

The -t flag is to tag the image as there can be different versions of the image.

Step 3: Docker compose

<!-- Image -->

Now, instead of starting the Foodtruck image and the Elasticsearch image separately and having to configure a network that will allow them to communicate, we can use a Docker Compose file. This allows us to start both containers with a single command, making the process much simpler.

The docker-compose file:

version: "3"
 services:
     es: 
        image: docker.elastic.co/elasticsearch/elasticsearch:6.3.2 
        container_name: es 
        environment: 
            - discovery.type=single-node
        ports: 
            - 9200:9200
        volumes: 
            - esdata:/usr/share/elasticsearch/data 
    web:
        image: yourusername/food-trucks 
        command: python3 app.py 
        depends_on: 
            - es 
        ports: 
            - 5000:5000 
        volumes:
            - ./flask-app: /opt/flask-app 
volumes: 
    esdata: 
        driver: local


The names of our services are defined at the parent level. The elastic search image is named "es" while the food truck service is named "web". It’s compulsory to include the image parameter for each service while additional parameters can be added for each service as needed. For the "es" service, we’ll refer to the "elasticsearch" image available on the Elastic registry. While we use the image built in step 2 for the backend server.

We have additional parameters such as the "ports" parameter which enables us to define the ports on the container that should be exposed and mapped to the host system and this will allow external access to the web app. The "volumes" parameter is optional and specifies a mount point in the "web" container where our code will reside. The “ depends_on” parameter is used to specify that the "web" service depends on the "es" service and this ensures that the "es" container is started before the "web" container thus allowing the "web" container to establish a connection with the Elasticsearch service.

To avoid making this post overly long, the concluding part of the project which is the deployment of the app will be covered in a separate blog post.


See Ya!!



