Installation
==========


## Build image :

```
docker build -t <yourname/imagename> .
```

## Run container from image on OS X:

Running this makes little to no sense because gparted can only access boot2docker's disk.

Start socat to expose local xquartz socket on a TCP port

```
socat TCP-LISTEN:6000,reuseaddr,fork UNIX-CLIENT:\"$DISPLAY\"
```

Pass the display to container (assuming virtualbox host is available on 192.168.59.3):

```
docker run -v /tmp/.X11-unix:/tmp/.X11-unix --device=/dev/sda:/dev/sda -e DISPLAY=192.168.59.3:0 --name gparted <yourname/imagename>
```

## Run container from image on Linux:

```
docker run -v /tmp/.X11-unix:/tmp/.X11-unix --device=/dev/sda:/dev/sda -e DISPLAY=unix$DISPLAY --name gparted <yourname/imagename>
```

Enjoy!
