# template-docker-www
![pknw1](https://i.imgur.com/QLE73JX.png)![nginx](https://i.imgur.com/gmRovtW.png)![ssl](https://i.imgur.com/5qo1GoK.png)![caddy](https://i.imgur.com/KJwjKa8.png)![ntfy](https://i.imgur.com/ZvgI8QM.png)

Configurable template repository to deliver static content using Caddy HTTP server in Docker

1. Commit and merge into Main branch
2. Select the "Build" manual action 
3. Set configuration values

  ```
  [docker_user]/[docker_image]:[docker_tag]          The output docker image details
  [hostname]                                         The Hostname and Proxy Virtual Host Name
  [hostport]                                         The Port to send proxied traffic 
  [deploy_stack]                                     Simple HTTP container or Proxied for SSL Termination
  ```
<details>
  <summary></summary>
   This second version includes the simple build to image and export as tar feature however by running Buiild & Deploy and selecting 
   "proxied version" it will deploy nginx frontend and setup for automatic SSL certs 

  If the machine running the container is behind a firewall and not reachable via http 80 for LetsEncrypt to perform verification for SSL issue, 
   you can either open port forwarding from your public IP through the router to host machine - but then close it aftertwrds
</details>

4. Click Run Workflow 


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
