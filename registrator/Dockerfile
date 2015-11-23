FROM dspfac/alpine-base:latest

ENV REGISTRATOR_PATH github.com/gliderlabs/registrator
ENV REGISTRATOR_REPO https://${REGISTRATOR_PATH}.git
ENV REGISTRATOR_BRANCH master
ENV GOPATH /usr

RUN apk add --update build-base git go  
RUN git clone -b ${REGISTRATOR_BRANCH} ${REGISTRATOR_REPO} ${GOPATH}/src/${REGISTRATOR_PATH} && \
  cd ${GOPATH}/src/${REGISTRATOR_PATH} && \
  go get && \
  go build -ldflags "-X main.Version $(cat VERSION)" -o /bin/registrator && \
  apk del build-base git go && \
  rm -rf /var/cache/apk/* && \
  rm -r /usr/src/*

ADD root /
WORKDIR /root
