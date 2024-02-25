# base image
FROM node:latest

# use specific user id when running the image
# by default, image is run by root (with limited permission as roor in the host node)
USER 1000

ENV MONGO_DB_USERNAME=admin \
    MONGO_DB_PWD=pwd

# execute commands in a new layer on top of the current image and commit the results.
# It's often used for installing software, modifying settings, and other setup tasks. 
# Each RUN command creates a new layer in the image.
RUN mkdir -p /home/app

COPY ./hello.js /home/app

# sets the user to use when running the image and for any RUN, CMD, and ENTRYPOINT instructions that 
# !!!! FOLLOW IT !!!!
# any RUN CMD ENTRYPOINT before USER, is run as root
USER daemon

# When a container starts, the executable specified by the ENTRYPOINT is run,
# any arguments passed to docker run <image> are appended to this ENTRYPOINT
ENTRYPOINT ["echo"]

# CMD provides default arguments to the ENTRYPOINT
# OR a default command to run if no ENTRYPOINT is specified
CMD ["Hello World"]

# docker run image_name              prints "Hello World"
# docker run image "Hello Again"     prints "Hello Again"