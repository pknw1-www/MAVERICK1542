# template-docker-www

## setup
- [X] Create a repository from the template

## publish (Mobirise)
- [X] clone to local machine
- [X] checkout a new branch
- [X] publish web content into the ```publish``` folder
- [x] verify push
- [X] merge into main when happy
- [X] execute the build github action
- [ ]   VEFY IMPORTANT - the image name has to escape the slash in the image name so it should be ```maverick1542\/web:latest```
- [ ] this will ctreatem a ```docker-compose.yml``` file
- [ ] this will create a docker image (named as you input)
- [ ] once completed click on the Workflow summary and you'll see 2 artifacts

## publish (3rd Party)
- [X] download the docker-compose zip and extract it
- [ ] download the docker-image zip and extract it
- [ ] import the archive to your docker images with ```docker import <your_image>:latest' < image.tar

as long as the image name matches the docker composr fileyou can start with ```docker compose up -d```
the container will run and serve your content from buildpublish
currently confiugred to expose port 8888 - this can be changed

http://localhost:8888/

```
services:
  maverick1542:
    image: maverick1542/web:latest
    container_name: web
    hostname: web
    ports:
      - 8888:80
```
