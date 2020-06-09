## Jenkins_Docker Project 2019 ##
Built a centos server using docker compose and installed Jenkins to run inside the container

## docker instalation on centos ##
* sudo yum install docker-ce
* sudo systemctl start docker
* sudo systemctl status docker
* sudo systemctl enable docker
* sudo usermod -aG docker <your_user_id>

## useful commands i've used throughout my learning experience ##
* docker-compose up -d ==> start the docker container in the background
* docker info | grep -i root ==> where docker is saving its files
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
* docker-compose up: see all of the docker containers currently running
* docker-compose up: start the docker container
* docker-compose down: remove all docker containers in the repository
* docker kill :container_id ==> remove a specific docker container
* docker-compose config ==> verify that the Compose file format is correct. If it is correct, the configuration is displayed. If the 
  format is incorrect, the cause of the error is displayed.
* docker-compose port ==> prints the public port to which a container port is mapped.
* docker-compose version ==> prints the version of docker-compose.
* docker-compose top ==> view the processes running within each service container.
* docker-compose pull <service> ==> pulls an image associated with a service defined in a docker-compose.yml
* docker-compose restart <service> ==> restarts all stopped and running services.
