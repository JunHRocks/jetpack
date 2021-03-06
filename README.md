#Machine Learning Tools in Docker

Machine learning tools are notorious for having byzantine dependencies and often academic code quality. This makes them hard to install and configure correctly across different machines and operating systems.  At  [Startup.ML](http://startup.ml/) we have been using Docker to simplify the process of getting these tools on our machines.

## Currently supported tools

* Deeplearning4J
* GraphLab
* H2O
* Julia
* MLlib
* Theano
* Torch7
* Vowpal Wabbit (VW)

## Getting started
* First step is to [Install Docker on Mac OS X](https://github.com/boot2docker/osx-installer/releases/download/v1.4.1/Boot2Docker-1.4.1.pkg). 
* Once Boot2Docker has been installed, launch it from Spotlight
* In the terminal window with the title "Boot2Docker for OSX" go to the jetpack directory and start the build process

To build an individual image, provide it as an arguement to the build.sh script.  Currently the following individual builds are supported: deeplearning4j, graphlab, h2o, julia, theano, torch7 & vw 

```
./build.sh julia
```

or to build all tools

```
./build.sh 
```

to run the docker image

```
./run.sh julia (or theano, graphlab, torch7, mllib ...)
```

to clean up (kill, remove container and remove image)

```
./clean.sh 
```


## Linux specific

The docker daemon must run as root. To be able to run the docker
client as a normal user, add that user to the docker group. To do so
for the current user, run: `sudo gpasswd -a ${USER} docker`.

See [docker documentation](https://docs.docker.com/installation/ubuntulinux/#giving-non-root-access)
for more detail.
