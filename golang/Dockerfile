FROM golang:1.22 AS builder

WORKDIR /app

COPY go.mod go.sum ./
RUN go mod download && go mod verify

COPY . .

RUN CGO_ENABLED=0 GOOS=linux go build -o fizzbuzz .

FROM gcr.io/distroless/static-debian12

WORKDIR /app

COPY --from=builder /app/fizzbuzz /fizzbuzz
COPY --from=builder /app/templates /templates

EXPOSE 8080

ENTRYPOINT ["/fizzbuzz", "serve"]