# Use an official Node.js runtime as the base image
FROM node:16

# Set the working directory in the container
WORKDIR /usr/src/app

# Copy the current directory contents into the container at /usr/src/app
COPY --chown=node:node . .

# install the app dependencies that are in the package.json file and omit the dev dependencies
# ci is used to install the dependencies in the package-lock.json file
RUN npm ci --omit=dev

# Set the environment variable DEBUG to playground:*
ENV DEBUG=playground:* 

# set the user to the node user
USER node

# start the app and listen on port 3000
CMD npm start