# docker-register

[![circleci][circleci]](https://circleci.com/gh/vektorcloud/docker-register)

A simple etcd service discovery container based on docker-gen. Containers with exactly one port published to the host will be registered in etcd at `/backends/<image_name>/<image_tag>/<image_id>`, e.g. `/backends/redis/latest/2f2ffba3ddf1`

# Usage

```bash
docker run -d \
           -e ETCD_HOST="127.0.0.1:4001" \
           -v /var/run/docker.sock:/var/run/docker.sock \
           vektorlab/docker-register:latest
```

An optional DOCKER_HOST variable can be provided as well(defaults to unix://var/run/docker.sock)

[circleci]: https://img.shields.io/circleci/build/gh/vektorcloud/docker-register?color=1dd6c9&logo=CircleCI&logoColor=1dd6c9&style=for-the-badge "docker-register"
