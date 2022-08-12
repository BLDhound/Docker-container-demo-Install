# Docker-container-demo-Install
# It contains a simple todo list manager that runs on node.js and we want to integrate it into a docker container
# The App contents were downloaded from https://docs.docker.com/get-started/02_our_app/#:~:text=getting%2Dstarted%20repository and extracted
# The App folder in the getting-started folder is extracted and opened using an IDE e.g Visual studio 
# A text file named Dockerfile (which is basically a text-based script of instructions that is used to create a docker image) is created in the same folder
as the package.json
# In the Dockerfile we write the following 

# syntax=docker/dockerfile:1
FROM node:12-alpine
RUN apk add --no-cache python2 g++ make
WORKDIR /app
COPY . .
RUN yarn install --production
CMD ["node", "src/index.js"]
EXPOSE 3000

# NB: Make sure the Dockerfile has no .txt extension
# Using terminal and on the App directory, build the container image using $ docker build -t getting-started .
# Start the container using $ docker run -dp 3000:3000 getting-started

# open your web browser to http://localhost:3000. You should see our app.
