# Serverdock
Simple golang app that we can run 24/7 in Docker.

## Build/Run Locally
* cd into your repo
* $ go mod init github.com/your/repo/serverdock
* go build
    * Creates an executable file that you can run
* ./serverdock

## Building with Docker
* Create your docker file in same directory as your Go webapp
* docker build --no-cache -t serverdock/webapp .
    * Don't forget the (.) && webapp is the container name && --no-cached is optional
* Now your image is created

## Running with Docker
* $ docker image ls         # This will show you all images built
* $ docker run -d -p 8080:8080 serverdock
    * returns your container ID
* $ docker container ls     # This will show your containers running

### Once your server is running
* Curl to our server at either http:127.0.0.1:8080 OR http://localhost:8080
* $ curl http://127.0.0.1:8080
* $ curl http://127.0.0.1:8080/articles
* If you have an app to do POST/GET requests you can use that as well (Postman)
* POST/GET http://127.0.0.1:8080/articles 

## Stopping Docker Container
* $ docker container -help
    * See the list of commands possible
* $ docker container stop <dockerID> OR webapp(name of container)
* returns <dockerID> OR webapp