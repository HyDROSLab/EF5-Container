# EF5-Container
Containerized version of EF5 for research applications.

This container includes a stand-alone EF5 built in Ubuntu.

## INSTRUCTIONS

Go to the location of the EF5-Container folder. For example:

cd ~/Documents/EF5-Container/

### Build EF5 Image

Within the EF5-Container folder, run the following command:

docker build -t ef5image Docker/

You should see a lot going on your screen. The process should take about 3 minutes. When finished, you should see the following text as the last line:

Successfully built 7c1310438e65

The "7c1310438e65" is the IMAGE ID automatically assigned to your EF5 image. It will be different for your own built. You can check your image with the following docker command:

docker images

You should at least see a list like the following:

REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
ef5image            latest              7c1310438e65        6 minutes ago       514.4 MB
ubuntu              latest              4ca3a192ff2a        22 hours ago        128.2 MB

### Start EF5 Container

docker run --env PATH=$PATH:/EF5/bin -d -ti --entrypoint=/bin/bash --name=EF5 ef5image

### Run EF5

docker exec EF5 ef5
