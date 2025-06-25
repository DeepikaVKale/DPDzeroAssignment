#Use the offical Golang base image from Docker Hub 
FROM golang:1.24.4-alpine

#set the working directory inside container  
WORKDIR /app

#Install dependencies for health check and debugging
RUN apk update && apk add --no-cache curl

#copy and install binary to container's app directory
COPY go.mod ./
RUN go mod download

#copy current directory contents to conatiner's app directory
COPY . /app/

#build and compile packages 
RUN go build -v -o service_1 .

#expose the port the app will run on
EXPOSE  8001

#command to run the app
CMD ["./service_1"]