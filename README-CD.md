Name: Denver Woolard

# Project 5

## CD Project Overview

  - For Project 5, we are building off of the CI we created to use it for CD, or Continuous Deployment. For the first section, we are updating ourgithub action workflow to use Semnatic Versioning. To not simply just overwrite all of our previous builds with the singular tag `latest`. Instead it will tag each build with version numbers and 'save' them for reference. So when a build is pushed, the previous build is not simply overwritten by 'latest' but saved as build 0.1.1 for example. This is once again using github actions to push to Docker, using a tool called docker/metadat-actions to generate the data for the tags. 

  - The second part of project 5 is about creating a server of sorts with the image we created. A running webserver that will update alongside updates pushed to the Dockerhub repository it originates from. A script will ensure the container restarts in order to the apply the updated changes as well as storing the previous version, much like semnatic versioning mentioned earlier. The webhook is used to easily communicate with the server and restart it when needed. This is all part of the Continuous Deployment process, ensuring the server is kept up tp date.

  ```mermaid
flowchart LR
A{Devs} -->|Git Commit| B{Shared Repository -Github}
B -->|Automatic Integration Tests| C(Test Enviornment)
C -->|Build Error| A
C -->|Build Success| D{Updated Repository}
D -->|Automatic Deployment| E{End Users/Servers}
```

  - You can generate a tag when pushing to github by simply using `git tag <tagname>`. For proper versioning you should use the 'Semantic Versioning' standard of `git tag v<major>.<minor>.<patch>`. You then simply push the created tag with `git push --tags`.

  - Our Github Workflow automates this process, by assigning a tag each time we push. The action I created will check for metadata using docker/metadata-actions and then append that to the build each time the 'push' action is done. This allows us to have Semantic Versioning and keep clean records of our previous builds, rather than only having a continuosly updated 'latest'.

  - https://hub.docker.com/repository/docker/wsudwoolard/project4/general

 ### Task 2

  - To install docker to a freshly configured instance, you first need to ensure the instance is running up to date. You can do this with `sudo apt update` followed by `sudo apt upgrade`. Once the system is updated we can install docker using a series of commands. First to install Docker itself you use `sudo apt install docker.io` Then to retrieve any dependencies it might need you can use `sudo snap install docker`. And with that, Docker is installed.
    
  - 
