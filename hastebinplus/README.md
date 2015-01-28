Installation
==========


## Build image :

```
docker build -t <yourname/imagename> .
```

## Run container from image :

```
docker run -p 8080:8080 -v /var/docker/hastebin/data:/opt/haste/data --name hastebin <yourname/imagename>
```

Enjoy!