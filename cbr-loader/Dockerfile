FROM golang:1.12-alpine as build

WORKDIR /go/src/github.com/max-samoylov/go-examples/cbr-loader
COPY . /go/src/github.com/max-samoylov/go-examples/cbr-loader

RUN go build -ldflags "-s -w" -o cbr-loader ./app


FROM alpine:3.9

COPY --from=build /go/src/github.com/max-samoylov/go-examples/cbr-loader/cbr-loader /srv/cbr-loader

ENTRYPOINT [ "/srv/cbr-loader" ]