FROM alpine:3.6

ENV GOOGLE_APPLICATION_CREDENTIALS=/etc/fission/google-credentials.conf

RUN apk update && \
	apk add --no-cache python3 python3-dev build-base && \
	pip3 install --upgrade pip && \
	rm -rf /root/.cache

COPY . /app
WORKDIR /app
RUN pip3 install -r requirements.txt

ENTRYPOINT ["python3"]
CMD ["server.py"]
