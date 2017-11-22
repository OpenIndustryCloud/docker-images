FROM golang:1.8.1

ENV GOPATH /usr
ENV GOOGLE_APPLICATION_CREDENTIALS=/tmp/google-credentials.conf


RUN go get github.com/fission/fission && \
	go get k8s.io/apimachinery/pkg/apis/meta/v1 && \
	go get k8s.io/client-go/kubernetes  && \
	go get k8s.io/client-go/rest && \
	go get cloud.google.com/go/storage && \
	go get github.com/mediocregopher/radix.v2/redis