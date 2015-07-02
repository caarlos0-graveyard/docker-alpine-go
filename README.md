# Alpine Golang

Alpine Golang is a docker image based in Alpine linux using a Dockerfile
similar to [google/golang](https://registry.hub.docker.com/u/google/golang/)
and based on [kiasaki/docker-alpine-golang](https://github.com/kiasaki/docker-alpine-golang).

This image is based on `alpine:3.2` image.

## Notes

- `GOROOT` is set to `/goroot`
- `GOPATH` is set to `/gopath`

# Usage

Create a Dockerfile in your Go application directory with the following content:

```
FROM caarlos0/alpine-go

WORKDIR /gopath/src/app
ADD . /gopath/src/app/
RUN go get app

CMD []
ENTRYPOINT ["/gopath/bin/app"]
```

Then you can run the following command in your application directory:

```
docker build -t my/app .
```
