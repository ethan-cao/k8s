# base image
FROM node:latest

# use specific user when running the image
# by default, image is run by root (with limited permission as roor in the host node)
USER 1000

ENV MONGO_DB_USERNAME=admin \
    MONGO_DB_PWD=pwd

# execute commands during the image build process. 
# It's often used for installing software, modifying settings, and other setup tasks. 
# Each RUN command creates a new layer in the image.
RUN mkdir -p /home/app

COPY ./hello.js /home/app

# When a container starts, the executable specified by the ENTRYPOINT is run,
# any arguments passed to docker run <image> are appended to this ENTRYPOINT
ENTRYPOINT ["echo"]

# CMD provides default arguments to the ENTRYPOINT
# OR a default command to run if no ENTRYPOINT is specified
CMD ["Hello World"]

# docker run image_name              prints "Hello World"
# docker run image "Hello Again"     prints "Hello Again"