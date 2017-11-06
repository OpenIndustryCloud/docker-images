FROM golang:1.8-alpine

# go option
ENV GO=go
ENV PKG=""
ENV TAGS=""
ENV TESTS=.
ENV TESTFLAGS=""
ENV LDFLAGS=""
ENV GOFLAGS=""

RUN apk update && \
	apk add --no-cache \
		git \
		curl \
		bash && \
	rm -rf /var/cache/apk/* 

RUN go get golang.org/x/tools/cmd/cover && \
	go get github.com/mattn/goveralls && \
	go get github.com/Masterminds/godir && \
	go get -u gopkg.in/alecthomas/gometalinter.v1 && \
  	gometalinter.v1 --install

CMD [ "/bin/bash" ]
