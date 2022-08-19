## Docker-container-demo-Install

1. It contains a simple todo list manager that runs on node.js and we want to integrate it into a docker container

2. The App contents were downloaded from [here](https://docs.docker.com/get-started/02_our_app/#:~:text=getting%2Dstarted%20repository) and extracted

3. The App folder in the getting-started folder is extracted and opened using an IDE e.g Visual studio 

4. A text file named **Dockerfile** (which is basically a text-based script of instructions that is used to create a docker image) is created in the same folder as the package.json

5. In the Dockerfile we write the following 

6. syntax=docker/dockerfile:1

- FROM node:12-alpine

- RUN apk add --no-cache python2 g++ make

- WORKDIR /app

- COPY . .

- RUN yarn install --production

- CMD ["node", "src/index.js"]

- EXPOSE 3000

**NB: Make sure the Dockerfile has no .txt extension**

Using terminal and on the App directory, build the container image using $ docker build -t getting-started .

Start the container using $ docker run -dp 3000:3000 getting-started
open your web browser to [local host](http://localhost:3000). You should be able to see our app.
