# EF5-Container
Containerized version of EF5 for research applications.

This container includes a stand-alone EF5 built in Ubuntu.

## INSTRUCTIONS

### Build EF5 Image

docker build -t ef5image .

### Start EF5 Container

docker run --env PATH=$PATH:/EF5/bin -d -ti --entrypoint=/bin/bash --name=EF5 ef5image

### Run EF5

docker exec EF5 ef5
