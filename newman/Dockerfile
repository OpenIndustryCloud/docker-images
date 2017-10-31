FROM node:8-alpine

ENV COLLECTION="/src/collection.json"
ENV ENVIRONMENT=staging
ENV FISSION_ROUTER=fissionrouter.default.svc.cluster.local
ENV COLLECTION=fission-src/ci/collection.json
ENV FUNCTION_NAME=foobar
ENV TARGET_PORT=80
ENV PROTOCOL=http

RUN apk update && \
	apk add --no-cache \
		curl \
		jq \
		bash && \
	rm -rf /var/cache/apk/* 

RUN	npm install -g newman && \
	npm cache clean --force

CMD [ "newman", "run", "${COLLECTION}" ]
