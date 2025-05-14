FROM golang:1.22

WORKDIR /usr/src/app

COPY go.mod .
COPY go.sum .

RUN go mod tidy && go mod verify

COPY . .

RUN go build -o fizzbuzz .

EXPOSE 8080

ENTRYPOINT ["./fizzbuzz", "serve"]