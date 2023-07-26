FROM golang:1.21rc3-alpine3.17 AS builder
WORKDIR /app
COPY go.mod go.sum ./
RUN go mod download
COPY . .
RUN CGO_ENABLED=0 go build -a -installsuffix cgo

FROM alpine:3.18
WORKDIR /app
COPY --from=builder /app/gin-app ./
EXPOSE 8080
CMD ./gin-app
