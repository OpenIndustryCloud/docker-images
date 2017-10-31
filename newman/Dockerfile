FROM node:8-alpine

ENV COLLECTION="/src/collection.json"

RUN	npm install -g newman && \
	npm cache clean --force

ENTRYPOINT [ "newman", "run", "${COLLECTION}" ]
