FROM golang:latest

WORKDIR /app

COPY . .

RUN go mod download

RUN go build -o /go/bin/service_1 ./

EXPOSE  8001

CMD [ "./service_1" ]