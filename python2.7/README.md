Installation
==========

This image is based on Alpine Linux for the sole purpose of being as small as possible. (less than 60MB)

## Build image :

```
docker build -t <yourname/imagename> .
```

## Run python REPL :

```
docker run --rm -it <yourname/imagename>
```

## Run python app/script :

```
docker run --rm -it -v `pwd`:/var/python -w /var/python <yourname/imagename> python your_script.py
```

Enjoy!