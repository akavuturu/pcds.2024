# Building the Parallel Computing EBook environment

These are instructions as to how to create a dockerized environment for the parallel programming eBook.

## Prepare your system

Install docker. Follow platform specific instructions

## Build container

docker build . -t pp.ebook

## Run container

This only runs out of the `environment` subdirectory in which you built the container.

docker run --shm-size=5gb -i -t --mount type=bind,source=./../ebook,target=/home/jupyteruser/ebook -p8888:8888 pp.ebook

docker run -i -t --mount type=bind,source=C:\Users\akavu\Desktop\pcds.2024\environment/../ebook,target=/home/jupyteruser/ebook -p8888:8888 pp.ebook

## Run jupyter in container

cd ebook

jupyter lab --ip 0.0.0.0
