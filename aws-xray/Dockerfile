FROM debian:stable-slim

RUN apt-get update \
    && apt-get install -y --force-yes --no-install-recommends apt-transport-https curl ca-certificates wget \
    && apt-get clean \
    && apt-get autoremove \
    && rm -rf /var/lib/apt/lists/*

RUN cd /tmp \
    && wget https://s3.dualstack.us-east-2.amazonaws.com/aws-xray-assets.us-east-2/xray-daemon/aws-xray-daemon-2.x.deb \
    && dpkg -i aws-xray-daemon-2.x.deb \
    && rm aws-xray-daemon-2.x.deb \
    && mkdir -p /root/.aws/

EXPOSE 2000/udp

COPY ./aws-xray-entrypoint /aws-xray-entrypoint

ENTRYPOINT ["/aws-xray-entrypoint"]
CMD ["/usr/bin/xray", "--bind=0.0.0.0:2000"]
