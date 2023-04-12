Name: Denver Woolard

# Project 5

## CD Project Overview

  - For Project 5, we are building off of the CI we created to use it for CD, or Continuous Deployment. For the first section, we are updating ourgithub action workflow to use Semnatic Versioning. To not simply just overwrite all of our previous builds with the singular tag `latest`. Instead it will tag each build with version numbers and 'save' them for reference. So when a build is pushed, the previous build is not simply overwritten by 'latest' but saved as build 0.1.1 for example. This is once again using github actions to push to Docker, using a tool called docker/metadat-actions to generate the data for the tags. 

  - The second part of project 5

  - You can generate a tag when pushing to github by simply using `git tag <tagname>`. For proper versioning you should use the 'Semantic Versioning' standard of `git tag v<major>.<minor>.<patch>`. You then simply push the created tag with `git push --tags`.

  - Our Github Workflow automates this process, by assigning a tag each time we push. The action I created will check for metadata using docker/metadata-actions and then append that to the build each time the 'push' action is done. This allows us to have Semantic Versioning and keep clean records of our previous builds, rather than only having a continuosly updated 'latest'.

  - https://hub.docker.com/repository/docker/wsudwoolard/project4/general

  

