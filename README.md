# Docker image Ubuntu 22.04 OpenMPI 

This project provides a Docker container for an HPC environment based on OpenMPI, OpenMP, and Ubuntu Linux.

## Use Docker Container

### Build the image

`docker build --no-cache -t dockermpi .`

### Run the container
`docker run --rm -it -v $(pwd):/project dockermpi `

