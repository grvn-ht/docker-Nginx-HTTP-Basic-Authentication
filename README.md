# docker-Nginx-HTTP-Basic-Authentication
Nginx server protected by HTTP Basic Authentification, -> with Docker Compose

If you want it to work right away you will need to clone this directory:

"
#git clone "https://github.com/grvn-ht/docker-Nginx-HTTP-Basic-Authentication.git" .
"

You will also need to build the Dockerfile into a "apache2-utils:v3" image personnalized:

"
#docker build . -t apache2-utils

#docker run -it apache2-utils:latest bash

#mkdir /etc/apache2

#touch /etc/apache2/.htpasswd

#htpasswd -c /etc/apache2/.htpasswd user1
"

then enter your password, confirm it, quit the container "ctrl+d" and commit it to a new image "apache2-utils:v3":

"
#docker commit <container-name> apache2-utils:v3

#docker-compose up
"

Remember to change the .env file or to change the example.com in nginx-conf/nginx.conf file into your own domain name.
