# docker_auth

https://github.com/cesanta/docker_auth/
https://the.binbashtheory.com/creating-private-docker-registry-2-0-with-token-authentication-service/

More advanced, with extensions https://medium.com/@maanadev/authorization-for-private-docker-registry-d1f6bf74552f

*Basic*
But, use docker-compose
```
$ docker run \
    --rm -it --name docker_auth -p 5001:5001 \
    -v `pwd`/config:/config:ro \
    -v /tmp/log/docker_auth:/logs \
    cesanta/docker_auth:1 --v=2 --alsologtostderr /config/config.yml
```

### Create cert

This is for TLS for anything to connect to this service (ie registry).

```
openssl req -x509 -newkey rsa:4096 -keyout config/key.pem -out config/cert.pem -days 365
```

