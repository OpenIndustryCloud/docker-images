FROM golang:1.8-alpine

RUN apk update && \
	apk add --no-cache \
		curl \
		bash \
		jq \
		sed \
		&& \
	rm -rf /var/cache/apk/* 

WORKDIR /go/bin
COPY wfcli .
RUN chmod +x wfcli

CMD [ "wfcli" ] 

