# template-docker-www

## setup
- [X] Create a repository from the template
- [X] Run the "Configure" action to setup folder and url variables
- [X] Set the folder name (the folder name under ```/etc/pknw1/docker``` that the repo resides)
- [X] Set the production URL mysite.pknw1.co.uk
- [X] DEV url will be set to dev-mysite.pknw1.co.uk
- [X] Run the "Install" action to create the server folder, compose files and config folder

## publish (Mobirise)
- [X] clone to local machine
- [X] checkout a new branch
- [X] publish web content into the ```publish``` folder
- [x] verify and merge

## publish (python)
- [X] clone to local machine
- [X] checkout a new branch
- [X] copy content into the ```build``` folder
- [x] verify and merge

## publish (3rd Party)
- [X] clone to local machine
- [X] checkout a new branch
- [X] customise any docker-compose/other changes
- [X] verify and merg
- [X] run stage 3 deploy action

## build
- [X] Run "Build and Deploy" to build the container, push to dockerhub and pull image on server

## Backup
- [X] Run "Commit and Push Config" to stop the compose, commit the config folder to the config repo and restart

## Automation
- [X] Run "Enable Autobuild" to automaticaly build and deploy on Merge to Main
