FROM golang:1.8-alpine

ENV RELEASE=0.3.0
ENV FISSION_ROUTER=1.2.3.4
ENV FISSION_URL=4.3.2.1

RUN apk update && \
	apk add --no-cache \
		curl \
		bash \
		jq \
		&& \
	rm -rf /var/cache/apk/* && \
	curl -L -o fission https://github.com/fission/fission/releases/download/${RELEASE}/fission-cli-linux && \
	chmod +x fission && \
	mv fission /usr/local/bin/

ENTRYPOINT [ "fission" ]