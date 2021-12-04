FROM golang:1.17.3 as build

ENV PATH $PATH:/usr/local/go/bin
ENV GO111MODULE=on
WORKDIR /go/src

COPY ./app/go.mod ./app/go.sum ./

RUN go mod download
COPY ./app .

RUN go get -u github.com/cosmtrek/air && \
    go build -o /go/bin/air github.com/cosmtrek/air

CMD ["air", "-c", ".air.toml"]