# A docker image for the func container.

# default variant is the official alpine node image (much smaller than the standard image)
FROM node:8-alpine

ARG NODE_ENV
ENV NODE_ENV $NODE_ENV
ENV GOOGLE_APPLICATION_CREDENTIALS=/etc/fission/google-credentials.conf

RUN mkdir -p /usr/src/app
WORKDIR /usr/src/app

COPY package.json /usr/src/app/

RUN apk update && \
	apk add --no-cache \
		libc6-compat make gcc g++ \
		python py-pip python-dev && \
	npm install node-gyp rebuild && \
	npm install && \
	npm cache clean --force 
COPY server.js /usr/src/app/server.js

CMD [ "npm", "start" ]

EXPOSE 8888