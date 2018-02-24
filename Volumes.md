Volumes outlast the life of a conatiner
Used for persistent data.

Example 

**MySql**

.Pull down and run the mysql image in a container (docker container run -d -p 3306:3306 --name db -e MYSQL_ALLOW_EMPTY_PASSWORD=True  -v mysql:/var/lib/msql mysql) 

.If you run docker container inspect mysql and look at the meta data you will see that there is a volume path i.e /var/lib/mysql

.You will also see in the meta data it is under mounts which means it gets its own space on the host and links to the /var/lib/mysql path in the container

If you give a volume a name when startig the container it means you can re-use that same volume you have named when spinning up new containers
If you dont give a volume name, a new volume will be created each time you spin up a container.

**Note: On Mac and Windows you wont be able to cd to the host path where the volume is stored,because the path is created in a linux environment behind the scenes. If your host is a linux server then you will be able to cd to that directory**

docker volume ls


**Bind Mounting**

Maps contents to 2 different folders 1 folder on host 1 on container

Example in docker-file-sample-2 in Udemy course 
1. cd into docker-file-sample-2 folder
2. run 'docker container run -d --name nginx -p 80:80 -v $(pwd):/usr/share/nginx/html nginx' (this will copy everything pwd and put it in the usr/share/nginx/html)
3. if you create a txt file on the host within the docker-file-sample-2 folder it will also be created on the container
4. Create file 'touch testme.txt'
5. ssh into container docker container exec -it nginx bash
6.cd into /usr/share/nginx/html and you will see the testme.txt file
