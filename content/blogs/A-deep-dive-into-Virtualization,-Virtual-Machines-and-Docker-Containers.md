---
title: "A Deep Dive Into Virtualization, Virtual Machines and Docker Containers"
date: 2023-05-19T20:53:06+01:00
draft: true
author: Rhoda
tags: 
image: /images/docker-banner.webp
description:
---

Hi guys! 👋

I've been away for so long but I'm back here. 🎉

I thought it would be nice to walk you through a project I worked on while I was away. 🏃‍♀️

The project is simply a containerized web application that allows users to find food trucks near their current location or search for food trucks. 🍔🚚 The app was containerized using Docker to simplify the deployment and scaling. 🐳

This is the first part, and I will be introducing the concept of Docker. 🎉 I will appreciate it if you share this newsletter with your friends and anyone you know who might be interested. 🙏

Stay tuned for more exciting updates and let's dive into the world of containerization together! 🌟

Virtualization, Virtual Machines, and Docker containers.

Imagine you have a Windows computer that consists of the following:

🔹 The harHi guys! 👋

I've been away for so long but I'm back here. 🎉

I thought it would be nice to walk you through a project I worked on while I was away. 🏃‍♀️

The project is simply a containerized web application that allows users to find food trucks near their current location or search for food trucks. 🍔🚚 The app was containerized using Docker to simplify the deployment and scaling. 🐳

This is the first part, and I will be introducing the concept of Docker. 🎉 I will appreciate it if you share this newsletter with your friends and anyone you know who might be interested. 🙏

Stay tuned for more exciting updates and let's dive into the world of containerization together! 🌟

Virtualization, Virtual Machines, and Docker containers.

Imagine you have a Windows computer that consists of the following:

🔹 The hardware component (CPU, RAM, and storage)

🔹 The operating system that controls how applications use these hardware resources. 

🔹The application layer where the applications reside.


<!-- Image -->

<div align="center">
    <img src=/images/docker1.webp>
</div>

 <br>  


What if you want to test a web application that you're developing, and you want to see how that works, and how it looks in different operating systems? You would need another computer/laptop where you would install a Linux/Mac operating system. I'm sure you will agree that this is not cost-effective.

This is where virtualization comes in.

Virtualization involves the creation of a computer-generated environment that is separate from the physical computing hardware, effectively simulating a computer within a computer. Simply put, virtualization allows you to create multiple virtual computers from the hardware and software components of a single computer. 

This is achieved using a software called Hypervisor. A hypervisor is a technology that allows the hosting of multiple virtual computers on a single physical computer.

So this means that as long as you have one computer with one operating system, you can install other operating systems on top of the host operating system; using a hypervisor such as VirtualBox. So basically now you are sharing the hardware resources of one machine to run multiple virtual machines, each with its virtual hardware resources(virtual CPU, virtual RAM, and virtual storage ).

<!-- Image -->

<div align="center">
    <img src=/images/docker2.webp>
</div>

 <br>  

Each virtual machine runs as an independent computer and is completely isolated from the other virtual machines and the host machine. So if something breaks inside that virtual machine. It won't affect the main operating system.

Just like a hypervisor, Docker is a virtualization software that enables us to create container-based applications.

Docker containers are like physical containers, but instead of storing physical goods, Docker containers are used to store and package application software. Each application is packaged with everything it needs to run(configuration files, dependencies, etc.). 

The key difference between virtual machines📦 and Docker🐳 containers is in the level of virtualization. Recall that a virtual machine boots up its own guest OS. Therefore, it virtualizes both the operating system kernel and the application layer while a Docker container virtualizes only the application layer, and runs on top of the host operating system.

<!-- Image -->
<div align="center">
    <img src=/images/docker3.webp>
</div>

 <br>  

While Docker containers and virtual machines may have some similarities and each of them has specific use cases, some differences make containers preferred over VMs for certain projects.

Because virtual machines boot up their OS, VMs can be as large as a few gigabytes or even terabytes and it takes quite a while for a virtual machine to come up. While a Docker image is typically lightweight because it shares the host operating system and can be created in seconds with a single command. 

Also, Docker containers are more portable compared to virtual machines. Assuming you want to test your application on a different system or you want to share the application with a teammate, rather than having to configure the new system environment for the application, all you need to do is to run the Docker container as the configurations or the library files needed for the application is already packaged in the container.

<!-- Image -->
<div align="center">
    <img src=/images/docker4.webp width="50%" height="30%">
</div>

 <br>  

🚀 Other important things to know about Docker:

Docker Image: Docker image contains everything (like application code, libraries, and configurations) needed to run an application. Docker images serve as a template for creating containers. Containers are created from images. A container is the actual running instance of an image.

Docker Hub: Docker Hub is a platform that allows developers to store, share, and distribute Docker images easily. Think of it as a central repository for Docker images, similar to a large online marketplace for Docker images.

For my FoodTruck project 🚚  , 

I created a Docker image

Pushed the image to Docker Hub

Created a Docker-compose file

Deployed the application on AWS ECS using EC2 as the launch type

I will be sharing more on this next time so look out for the next article😉

Thank you for reading through❤️ 

If you have any specific topics you'd like us to cover or questions you'd like answered, please feel free to reach out to me

🎉 Fun Fact: Did you know that the first computer bug was an actual insect? In 1947, a moth caused a malfunction in the Harvard Mark II computer, and technicians discovered the "bug" trapped in a relay. From that moment on, the term "debugging" was born!