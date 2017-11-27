# LearnDocker

docker pull [image name]
docker run [image name]
docker images
docker ps 

docker run -p 80:80 kitematic/hello-world-nginx
docker ps
docker stop <contaier id>
docker ps -a
docker rm <>

docker rmeove image > docker rmi 

docker ps -a --no-trunc (for not truncate)
ls env:\  (list all environent variable)
ls hkcu:\ (list all registry current user)

docker save <images> -o <name>.tar

alpine light version of alpine

docker run --rm -v C:\Dexter\pluralsight\docker-windows-getting-started\materials:/data alpine ls /data

docker run --rm -it -p 8080:80 -v  C:\Dexter\pluralsight\docker-windows-getting-started\materials\solitaire\app:/usr/share/nginx/html:ro nginx

docker cp (copy fiile from host to container)

docker cp .\app\. <containername>:<destination to copy>

docker commit (take snap shot of vm to create image)
docker commit <name of image> <name:tag>
docker images

docker history <image name> --no-trunc


---------------
tcp://192.168.99.100

create a container columne that point to source code

image - is set of read only layer
thin R/w layer -container layer
volume - special type of directory in a container typically referred to as a data volume

can be shared and reused among container
data volume are persisted

docker run -p 8080;3000 -v /var/www node
docker inspect mycontainer

ctrl p Q -> don't kill the app in foreground -it 

Docker file

From Nginx
COPY app /user/share/nginx/html

docker build -f Dockerfile -t <tag image>

FROM microsoft/iis:nanoserever
Copy app c:/inetpub/wwwroot

--build the docker file

------------
docker-compose  automate the process of creating container

version:'2'
services:
	db:
		image:mysql
		ports:
			-3306:0006
		environment:
			-MYSQL_ROOT_PASSWORD=my-secret-pw
		volumnes:
			-db:/var/lib/mysql
	web:
		image:nginx
		ports:
			-8080:80
		enviornment:
			-MY_DB_PORT=3306
			-MY_DB_HOST=db
		volumes:
			-/my/php/app:/usr/share/nginx/html

docker-compose help up

docker-compose up 

docker network ls
docker volume ls

docker-compose exec postgress bash

--connecting container
docker run --name alpine --rm --net teamcity_default -it alpine sh

docker-compose ps (run with in the folder docker compse file)
docker compose rm -v
docker-compose down (bring network down)

https://github.com/friism/MusicStore/blob/master/docker-compose.windows.yml

Docker run reference
Docker file reference
Docker compose up 

docker logs 466  (check the logs)




---------
dockerfile instruction
 - from 
 - maintainer 
 - run
 - copy
 - 

eg: 
from  node
Maintainer Vimal Kumar
Copy 
WorkDir
Run
Expose
EntryPoint

docker build -t <your username>/node .


