FROM alpine:3.7

MAINTAINER Filip Procházka <filip.prochazka@cogvio.com>

RUN apk add --update \
    rsyslog \
  && rm -rf /var/cache/apk/*

EXPOSE 514/udp
EXPOSE 514/tcp

# for some reason, the apk comes built with a v5 config file. using this one for v8:
COPY ./etc/rsyslog.conf /etc/rsyslog.conf
COPY ./etc/rsyslog.d/mark.conf /etc/rsyslog.d/
COPY ./rsyslog-entrypoint /rsyslog-entrypoint

ENTRYPOINT ["/rsyslog-entrypoint"]
CMD ["rsyslogd", "-n"]
