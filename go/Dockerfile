FROM golang:1.19-alpine

ARG GOPROXY

WORKDIR /app

COPY go.mod ./
COPY go.sum ./

RUN go mod download
COPY *.go ./
RUN env && \
    export GONOSUMDB=example.com && \
    export GOPROXY=$GOPROXY && \
    go build -o /main
CMD [ "/main" ]
