# Docker image Ubuntu 22.04 OpenMPI 

This project provides a Docker container for an HPC environment based on OpenMPI, OpenMP, and Ubuntu Linux.

## Use Docker Container

Run the container in a directory where you have your C files to compile and run.

### Run the container from public image
You can use a public docker image which requires no cloning and building. The image is available for amd64 and arm64.
```shell
docker run --rm -it -v $(pwd):/project ghcr.io/olegbilovus/docker-mpi:master
```

### Build the image
Alternatively, you can build the image locally.
```shell
git clone https://github.com/olegbilovus/docker-mpi
cd docker-mpi
docker build --no-cache -t dockermpi .
```

#### Run the container from local build
```shell
docker run --rm -it -v $(pwd):/project dockermpi
```

## Visual Studio Code Tasks
[tasks.json](.vscode/tasks.json) can be saved in `<my-repo>/.vscode/tasks.json` of any repository to quickly run `mpicc` and `mpirun` on a file in Visual Studio Code.

The tasks are visibile in `Terminal->Run Task...`

Before running a task, open the target file and keep it in focus.


## Troubleshooting

- `/usr/bin/ld: cannot open output file` if you get this error when running `mpicc -g file.c -o file`, make sure _user, group and **others**_ have _read_ and _**write**_ permissions to the `file.c`.
