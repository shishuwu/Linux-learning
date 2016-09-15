FROM alpine:latest
MAINTAINER shishuwu<shuwu.shi@gmail.com>

RUN apk --no-cache add wget gzip && cd /
RUN wget https://github.com/shadowsocks/shadowsocks-go/releases/download/1.1.5/shadowsocks-server-linux64-1.1.5.gz --no-check-certificate

RUN gzip -d shadowsocks-server-linux64-1.1.5.gz
RUN mv shadowsocks-server-linux64-1.1.5 server
RUN chmod +x server
RUN apk del wget gzip
RUN rm -rf /var/cache/apk/*

EXPOSE 8899
ENTRYPOINT ["/server", "-p", "8899", "-k", "password","-m","aes-256-cfb"]