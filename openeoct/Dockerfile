FROM golang:1.12-alpine

RUN apk update && apk add git && rm -fr /var/cache/apk/*

WORKDIR /openeoct
COPY openeoct.go /openeoct/
COPY openapi*.json /openeoct/
RUN go get github.com/getkin/kin-openapi/openapi3 github.com/getkin/kin-openapi/openapi3filter github.com/urfave/cli github.com/BurntSushi/toml
RUN go build openeoct.go

ENTRYPOINT ["/openeoct/openeoct"]
CMD ["config", "config.toml"]
