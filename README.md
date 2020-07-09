=============

## Docker course ##
```
Challenge 1:
GOAL: create a Linux centos server
Built a centos server, created a remote_user, configured ssh & installed MySQL 
using a dockerfile & docker-compose.

Challenge 2:
GOAL: create a web server
1. use a centos base image
2. install the web server (httpd)
3. copy the tar file & extract in the relvant path: /var/www/html
4. start the web server 
5. pass the parameters: "-D" and "FOREGROUND"
6. call the image challenge: challenge:1
7. runs port 80 is open

```

```
## What is docker compose & docker ? ##
===
Docker is a tool designed to make it easier to create, deploy, and run applications by using containers from
a localhost to an on-premises data center and even the cloud.
Containers allow a developer to package up an application with all of the parts it needs, such as libraries
and other dependencies (both from the underlying OS and from other containers) and deploy it as one package
whereas docker-compose is a light weight tool for defining and running multi-container Docker containerized
apps in a single machine.
Docker containers virtualizes the OS kernel and not the actual HW
===
## Difference between an image vs container ? ##
an image is a set of instructions used to create the desired environemnt we desire, we start with a base image
and build the app server on top of it whereas a container is a running instance of that image
when we deploy a docker image to any env. it becomes a container.    

```
## some of the benefits of using docker ##
```
* Portability: you can deploy it to any other system regardless of what they're running on as long as the is a
               docker daemon running and you can be sure that your application will perform exactly as it did 
               when you tested it; this makes testing & dubbuging easier. 
               
* Performance:  the fact that containers do not contain an OS (whereas virtual machines do) means that containers 
                are  much smaller than virtual machines, are faster to create, quicker to start, you can run more
                of them, they're easier to distribute and modify. Less overhead.
                
* Agility: enables faster software delivery cycles as Docker works well as part of CI pipelines with tools 
           like Travis, Jenkins and therefore better application development.
           
* Docker Hub: For common or simple use cases, such as a LAMP stack, the ability to save images and push them to Docker
              Hub means that there are already many well-maintained images available. Being able to quickly pull a premade
              image or build from an officially-maintained Dockerfile can make this kind of setup process extremely 
              fast and simple 

using docker means we dont have to worry about package management or compiling codes on our machines, which will
or might be different from the machine our apps runs on, this saves time and make dev. process more reliable. 
```

## docker & docker-compose instalation on centos ##
```
* sudo yum install docker-ce
* sudo systemctl start docker
* sudo systemctl status docker
* sudo systemctl enable docker
* sudo usermod -aG docker <your_user_id>
* docker-compose: https://docs.docker.com/compose/install/
* Jenkins docker image: https://hub.docker.com/_/jenkins/
```
## useful docker commands i've learnt ##
```
=== Docker images management
*
*
*
*
*
*
*
*
*




=== Docker-compose management
* docker-compose up -d ==> start the docker container in the background
* docker info | grep -i root ==> where docker is saving its files
* sudo du -sh /var/lib/docker ==> how much space docker uses on your machine
* docker logs -f <container> ==> check your container's logs 
* docker-compose stop ==> stop the service
* docker-compose restart <container> ==> restart the container
* docker-compose down ==> delete the service but it wont delelte the volume
* docker-compose up -d  ==> the service will be re-created using files in the volume
* docker exec -ti <container> bash ==> ssh into the container/work inside the container
* docker cp script.sh <container>:/path/script.sh ==> copy the script file from your machine to container & specify the location
* docker-compose build ==> Under the project directory,  run docker-compose build to build (rebuild) the service.
* docker images ==> list your docker images
* docker cp remote-key <container>:/tmp/remote-key ==> copy keys to the container to allow passwordless ssh
* ssh -i /tmp/remote-key remote_user@hostname> ==> ssh into the container 
* docker rm -fv <container-name> ==> delelte a container
* docker cp table.j2 web:/var/www/html/index.php ==> copy that file to the container
* docker ps ==> list your running containers
* docker-compose start <service> ==> starts an existing service container.
* docker-compose stop
* docker-compose pause <service> ==> pauses running containers of a service. They can be unpaused with docker-compose unpause
* docker-compose unpause
* docker-compose up ==>  start the docker container
* docker-compose down ==>  remove all docker containers in the repository
* docker kill :container_id ==> remove a specific docker container
* docker-compose config ==> verify that the Compose file format is correct. If it is correct, the configuration is displayed. If the 
  format is incorrect, the cause of the error is displayed.
* docker-compose port ==> prints the public port to which a container port is mapped.
* docker-compose version ==> prints the version of docker-compose.
* docker-compose top ==> view the processes running within each service container.
* docker-compose pull <service> ==> pulls an image associated with a service defined in a docker-compose.yml
* docker-compose restart <service> ==> restarts all stopped and running services.
```

ref: https://warp-9.com/courses/enrolled/892658
