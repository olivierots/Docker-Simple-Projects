Docker challenge

GOAL: create a web server

1. use a centos base image
2. install the web server: yum -y install httpd
3. copy the tar file & extract in the relvant path: /var/www/html
4. start the web server using: /usr/sbin/httpd
5. pass the parameters: "-D" and "FOREGROUND"
6. call the image challenge: challenge:1
7. runs port 80 is open


own notes:
The CMD is passing in parameters. In this case we don’t want the service/process running in the background.
To breakdown ENTRYPOINT vs CMD:
ENTRYPOINT is the command you want to run.
CMD are the parameters you want to pass into the command.

docker run -p 8080:80 challenge:1 
