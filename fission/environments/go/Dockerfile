FROM golang:1.8.1

ENV GOPATH /usr
ENV APP	   ${GOPATH}/src/github.com/fission/fission/environments/go
ENV GOOGLE_APPLICATION_CREDENTIALS=/tmp/google-credentials.conf

ADD context	    ${APP}/context
ADD server.go   ${APP}

WORKDIR ${APP}
RUN go get && \
	go get k8s.io/apimachinery/pkg/apis/meta/v1 && \
	go get k8s.io/client-go/kubernetes && \
	go get k8s.io/client-go/rest && \
	go get cloud.google.com/go/storage && \
	go get github.com/mediocregopher/radix.v2/redis && \
	go get github.com/rubyphunk/goamz/aws && \
	go build -o /server server.go

ENTRYPOINT ["/server"]
EXPOSE 8888
