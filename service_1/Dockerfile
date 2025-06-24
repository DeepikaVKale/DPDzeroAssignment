FROM golang:1.23-alpine

WORKDIR /app

COPY go.mod ./
RUN go mod download

COPY . /app/

RUN go build -v -o service_1 .

EXPOSE  8001

CMD ["./service_1"]