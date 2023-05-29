# Go-KrakenD

Go-KrakenD is a simple implementation of KrakenD with a GoLang based MVC Application. A brief overview about this app is that it has a few services made on ```GoLang``` using ```gin-gonic1```. Then, This project is served on
```PORT 9000```. Afterwards, We use ```KrakenD``` as an API Gateway which basically uses the services served on ```PORT 9000``` and seamlessly creates a ```microservice architecture``` from ```krakend.json``` file. Since,
```KrakenD``` doesn't work on windows so I have also setup a DockerFile to make the project setup easier. So, **YOU NEED TO HAVE DOCKER INSTALLED IN YOUR SYSTEM IN ORDER TO RUN THIS APPLICATION**.<br/>
I have broken down the setup of this application in multiple steps, They are as follows:

## Step 1
```
go get
```
Run this command to install all the dependencies of the ```GoLang``` Project.

## Step 2
```
go mod tidy
```
Run this command to clear all the warnings and to make sure everything is perfect.

## Step 3
```
go build
```
Run this to create a fresh build to start.

## Step 4
```
./golang-jwt-project
```
Now, Run this command to serve the ```GoLang``` Project.

## Step 5
Firstly, Move from the root directly to the underlying directory ```KrakenDAPIGateway```:
```
cd KrakenDAPIGateway
```
Then, run this command to build for a new container
```
docker build . -t api-gateway-v1 --no-cache
```
Afterwards, Use this command to start the ```docker``` container.
```
docker run -it -p "3000:3000" api-gateway-v1
```
