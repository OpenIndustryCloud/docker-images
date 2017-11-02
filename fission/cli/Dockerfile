FROM golang:1.8-alpine

ENV RELEASE=0.3.0
ENV FISSION_ROUTER=1.2.3.4
ENV FISSION_URL=4.3.2.1

RUN apk update && \
	apk add --no-cache \
		curl \
		bash && \
	rm -rf /var/cache/apk/* && \
	curl -Lo fission https://github.com/fission/fission/releases/download/v${RELEASE}/fission-cli-linux && \
	chmod +x fission-cli-linux && \
	mv fission /usr/local/bin/fission

ENTRYPOINT [ "fission" ]