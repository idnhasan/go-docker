# go-docker

Several Examples for building docker containers for your Go applications.

Running the app locally

$ go build
$ ./go-docker
2019/02/03 11:38:11 Starting Server

$ curl http://localhost:8080?name=Hasan
Hello, Hasan

#Building and running the docker image
$ docker build -t go-docker .
$ docker image ls
$ docker run -d -p 8080:8080 go-docker
$ docker container ls
$ docker container stop ID =Container

#Dockerfile.volume
$ docker build -t go-docker-volume -f Dockerfile.volume .
$ mkdir -p ~/logs/go-docker
$ docker run -d -p 8080:8080 -v ~/logs/go-docker:/app/logs go-docker-volume
$ tail -200f ~/logs/go-docker/app.log

#Dockerfile.multistage
$ docker build -t go-docker-optimized -f Dockerfile.multistage .
