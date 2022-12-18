FROM golang:latest as builder

ENV CGO_ENABLED=0
ENV GOOS=linux
ENV GOARCH=amd64
WORKDIR /go/src/github.com/otsukatsuka/cloudrun
COPY . .
RUN go build main.go

FROM alpine
COPY --from=builder /go/src/github.com/otsukatsuka/cloudrun /app

EXPOSE 8080

CMD ["/app/main"]

