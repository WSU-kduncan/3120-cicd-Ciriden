3120-cicd-Ciriden created by GitHub Classroom

Name: Denver Woolard

# Project 4

## CI Project Overview

  - By creating an image of a webserver, it allows one to quickly set up a website wherever they might need. A small bit of html tweaking can see the site adjusted to suit the needs of whoever might need a website quickly. Skipping the proccess of installing/setting up Apache and such on a server. With an image like this, you could simply pull it to a new instance of choice and deploy it quickly en masse, instead of going to each one individually to apply settings and get the webserver running. This project is essentially taking those steps and condensing them to a quick, easy to run program that sets up a webserver automaitcally. By packaging the needed commands and html files in an image, when run it takes all the steps needed. This uses Apache to run the actual webserver and Docker to create the image and container, as well as to pull the needed files.

  - Steps to create the enclosed image.
    - On a Windows system, the first step is to install WSL2. This can be done with a simple command through the command prompt. `wsl --install` as an administrator. Then opening WSL2 after a restart you should first update and upgrade your linux packages with `sudo apt-get update` and then `sudo apt-get upgrade`. After doing so, you can install Docker Desktop `https://www.docker.com/products/docker-desktop/`.
    - After ensuring Docker is set to use WSL2 in the settings and after you have pulled the included Dockerfile + html. You can build the image by running the command `docker build -t <insertnamehere> .` This will create an image using the Dockerfile and the files including the html needed for the server. 
    - To run the created image and create a container, you use `docker run -d --name <insertnamehere> -p 80:8080 <previouslycreatedimagename>` The ports 80:8080 can be changed to the specific one the system is desired to use.
    - To ensure the webserver is working correctly, you can open a browser and go to `localhost:8080` or whichever port you specified in the previous step. This should display the html that was included, or customized.
