# docker-go

To get the sizes of the images generated you can run `docker images | grep test/`

### Dockerfile1 
A full GoLang image.
The image itself can recompile the code.
The most heavy resulting image.
~ 790 mb.

`docker build -f Dockerfile1 -t test/go1 . `

`docker run -p 8080:8080 test/go1:latest`

### Dockerfile2
The first attempt on multi stage building.
We use one image for building and another to run the project.
The builded project can run on all OS.
Ssh to that container is still possible.
Docker -v > 17.05
~11 mb.

`docker build -f Dockerfile2 -t test/go2 . `

`docker run -p 8080:8080 test/go2:latest`

### Dockerfile3
We use one image for building and another to run the project.
The builded project can run on all OS.
Ssh to the container is no longer possible.
Docker -v > 17.05
~ 6.6 mb

`docker build -f Dockerfile3 -t test/go3 . `

`docker run -p 8080:8080 test/go3:latest`

### Dockerfile4
We use one image for building and another to run the project.
The builded project can NO longer run on all OS.
Ssh to the container is no longer possible.
Docker -v > 17.05
~ 6.54 mb

`docker build -f Dockerfile4 -t test/go4 . `

`docker run -p 8080:8080 test/go4:latest`


