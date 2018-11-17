FROM alpine:3.8

MAINTAINER Filip Procházka <filip.prochazka@cogvio.com>

ENV TZ=/etc/localtime

RUN apk add --update \
    rsyslog \
  && rm -rf /var/cache/apk/*

EXPOSE 514/udp
EXPOSE 514/tcp

# for some reason, the apk comes built with a v5 config file. using this one for v8:
COPY ./etc/rsyslog.conf /etc/rsyslog.conf
COPY ./etc/rsyslog.d/remote.conf /etc/rsyslog.d/
COPY ./rsyslog-entrypoint /rsyslog-entrypoint

ENTRYPOINT ["/rsyslog-entrypoint"]
CMD ["rsyslogd", "-n"]
