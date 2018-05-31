# cogvio/rsyslog

Inspired by [voxxit/rsyslog](https://github.com/voxxit/dockerfiles/tree/18885593b548e7502b245ba287be68874e051bdf/rsyslog), thanks [Josh](https://github.com/voxxit/)!

This image is intended to be used as aggregator for [papertrail](https://papertrailapp.com)

## Usage: docker-compose

The environment variables `SYSLOG_HOST` and `SYSLOG_PORT` are mandatory

```sh
services:
  logs:
    image: cogvio/rsyslog:latest
    environment:
      - SYSLOG_HOST=logs*.papertrailapp.com
      - SYSLOG_PORT=123
```
