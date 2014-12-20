Installation
==========


## Build image :

```
docker build -t <yourname/imagename> .
```

## Run container from image :

```
docker run --privileged -p 1194:1194/udp -p 1194:1194/tcp -p 9700:9700/tcp -p 27017:27017 --name miniflux <yourname/imagename>
```

Enjoy!