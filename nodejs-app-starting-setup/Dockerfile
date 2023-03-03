# Pull the latest version of the node image from docker hub
FROM node:latest


# Change the working directory of the container to the /app directory
WORKDIR /app

# Copy all the content from the local directory containing the Dockerfile 
# to the /app directory of the docker container
COPY . /app

# Run the commands to prepare the image for the nodejs app
RUN npm install

# Now our container is ready based on the image template with all the necessary code and packages
# It's time now to work on the container
# First expose the port on which our nodejs app will run inside the container
EXPOSE 80

# Run the commands to run the nodejs app inside the container
CMD ["node","server.js"]

# Some More information about the ports and running the container from your local command line

# I just want to clarify again, that EXPOSE 80 in the Dockerfile in the end is optional. It documents that a process in the container 
# will expose this port. But you still need to then actually expose the port with -p when running docker run. 
# So technically, -p is the only required part when it comes to listening on a port. 
# Still, it is a best practice to also add EXPOSE in the Dockerfile to document this behavior.

# As an additional quick side-note: For all docker commands where an ID can be used, you don't always have to copy / write out the full id.

# You can also just use the first (few) character(s) - just enough to have a unique identifier.

# So instead of

# docker run abcdefg
# you could also run

# docker run abc
# or, if there's no other image ID starting with "a", you could even run just:

# docker run a
# This applies to ALL Docker commands where IDs are needed.

# For building image , just run the command : docker build .
# For running the container based on the given image id use : docker run <image id>
# For listing all running containers : docker ps
# For listing all containers : docker ps -a

# Images are "Read-Only" , so after making any changes to the code or dockerfile 
# you have to rebuild the image

#Images are Layer-based i.e on rebuilding the image only the changes in the code are executed again
# Docker does this by using the images caches whereever no change is done

