Installation
==========


## Build image :

```
docker build -t <yourname/imagename> .
```

## Run container from image :

```
docker run -p 8081:8081 --name shout <yourname/imagename> --port 8081
```

Enjoy!
