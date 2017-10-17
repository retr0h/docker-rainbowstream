FROM jfloff/alpine-python:2.7-slim
LABEL maintainer "John Dewey <john@dewey.ws>"

RUN /entrypoint.sh \
  -a zlib-dev \
  -a jpeg-dev \
  -a gcc \
  -a libc-dev \
  -p rainbowstream

CMD ["rainbowstream"]
