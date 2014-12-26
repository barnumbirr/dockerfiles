Installation
==========

## Edit config files to fit your needs.

## Build image :

```
docker build -t <yourname/imagename> .
```

## Run container from image :

```
docker run -p 6667:6667 -p 6697:6697 --name ircd-hybrid <yourname/imagename>
```

Enjoy!