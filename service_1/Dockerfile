FROM golang:1.24.4-alpine

WORKDIR /app

RUN apt-get update && apt-get install -y curl && rm -rf /v

COPY go.mod ./
RUN go mod download

COPY . /app/

RUN go build -v -o service_1 .

EXPOSE  8001

CMD ["./service_1"]