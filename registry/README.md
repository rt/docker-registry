# Registry

https://docs.docker.com/registry/

The registry uses it's own config to connect to the auth server
The cert.pem is the pair the auth server

Running from this directory.

```
docker run -p 5000:5000 --restart=always --name registry \
-v `pwd`/config/config.yml:/etc/docker/registry/config.yml \
-v `pwd`/config:/config \
-v /tmp/registry:/var/lib/registry \
registry:2
```
