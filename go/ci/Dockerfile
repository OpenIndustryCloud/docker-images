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

RUN go get k8s.io/apimachinery/pkg/apis/meta/v1 && \
	go get k8s.io/client-go/kubernetes && \
	go get k8s.io/client-go/rest && \
	go get golang.org/x/tools/cmd/cover && \
	go get github.com/mattn/goveralls && \
	go get github.com/Masterminds/godir && \
	go get -u gopkg.in/alecthomas/gometalinter.v1 && \
  	gometalinter.v1 --install

CMD [ "/bin/bash" ]
