https://docs.docker.com/engine/reference/builder/

**Run Dockerfile**

docker image build -t custom_nginx . (first time you run it may take longer,after that it will be cached and will spin up quickly)

TIP 
Ordering of a dockerfile is important. 
Keep commands that change the least at the top and commands that change the most at the bottom
Reason:
if a line is changed at the top, the rest of the image in the dockerfile has to be rebuilt.
Whereas if you change a line near the bottom, then most of the file will be cached when been re-built

**Sample Dockerfile**

 - you should use the 'node' official image, with the alpine 6.x branch
- this app listens on port 3000, but the container should launch on port 80
 so it will respond to http://localhost:80 on your computer
- then it should use alpine package manager to install tini: 'apk add --update tini'
- then it should create directory /usr/src/app for app files with 'mkdir -p /usr/src/app'
- Node uses a "package manager", so it needs to copy in package.json file
- then it needs to run 'npm install' to install dependencies from that file
- to keep it clean and small, run 'npm cache clean --force' after above
- then it needs to copy in all files from current directory
- then it needs to start container with command 'tini -- node ./bin/www'
- in the end you should be using FROM, RUN, WORKDIR, COPY, EXPOSE, and CMD commands

FROM node:6-alpine

EXPOSE 3000

RUN apk add --update tini && mkdir -p /usr/src/app

WORKDIR /usr/src/app

COPY package.json package.json

RUN npm install && npm cache clean --force && pwd && ls -al

COPY . .

RUN pwd && ls -al

CMD ["/sbin/tini", "node", "./bin/www"]


**docker image build -t my_first_image .**

**docker container run -p 80:3000 my_first_image**


**DOCKERFILE BEST PRACTICES**

Alpine is good for testing purposes, very lightweight

Image must start with a from command, either existing image or from scratch

https://kapeli.com/cheat_sheets/Dockerfile.docset/Contents/Resources/Documents/index

docker images -a (Will List Intermidiary Images As Full Image Is Been Built, This called the image cache)
docker images --filter "dangling=true"
