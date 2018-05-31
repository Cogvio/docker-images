# cogvio/aws-xray

See [Running the X-Ray Daemon on Amazon ECS](https://docs.aws.amazon.com/xray/latest/devguide/xray-daemon-ecs.html)

## Usage: docker-compose

```sh
services:
  aws-xray:
    image: cogvio/aws-xray:latest
    environment:
      - AWS_REGION=eu-central-1
      - AWS_ACCESS_KEY_ID=abc
      - AWS_SECRET_ACCESS_KEY=123
```

on your local machine (for testing purposes), you might want to add

```sh
    ports:
      - "127.0.0.1:2000:2000/udp"
    command: /usr/bin/xray --bind=0.0.0.0:2000 --local-mode
```
