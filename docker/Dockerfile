FROM golang:1.15.0-buster

USER root
ENV DEBIAN_FRONTEND=noninteractive

WORKDIR /tmp
RUN git clone https://github.com/gohugoio/hugo.git -b v0.79.1 && \
    cd hugo && \
    go install --tags extended && \
    cd .. && \
    rm -rf hugo

WORKDIR /hugo

EXPOSE 31313

CMD [ "hugo", "server", "--watch=true", "-D", "-F", "-b", "http://localhost:31313", "--bind=0.0.0.0", "--port=31313" ]