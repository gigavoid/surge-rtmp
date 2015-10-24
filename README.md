The Surge RTMP streaming server
=====================

Based on brocaar's [nginx-rtmp-module](https://github.com/brocaar/nginx-rtmp-dockerfile)


Running With Runscript
------
The runscript included in the `bin` folder is intended to be run from outside of the docker container. It can be used for simple servers which require no special features such as container linking. It supports both daemon and interactive mode. You can see all available options by running

```
./surge-rtmp -h
```

A few examples:

````
# A default server running interactively with port 1935 for RTMP and 1936 for HTTP stats. It will build a local version of the docker image.
./surge-rtmp

# Daemon mode with custom ports, 80 for web interface and 1025 for rtmp, using the locally built image.
./surge-rtmp -d -w 80 -r 1025

# Daemon mode with default ports but downloading a prebuilt image from dockerhub.
./surge-rtmp -p
```

All examples that build the docker file locally expects that the `Dockerfile` is in one directory up from the working directory. If you only will use dockerhub images (-p), feel free to move the runscript whereever.

Running Manually
------
If you want to run the server by first building it, please see the Building section below.

There are automated builds for this project at our [Docker Hub](https://hub.docker.com/r/gigavoid/surge-rtmp), which can be run without even cloning this repository. For example:

```
docker run --restart=always --name surge-rtmp -p 1936:1936 -p 1935:1935 -d gigavoid/surge-rtmp
```


Building
-------
There are two scripts in the `bin` folder that either can be used as is or modified to use settings that match your setings (such as ports).

`run-foreground` is great for development - it runs the script blocking and a `CTRL-c` is enough to quit it.

`run-background` will put the server in a daemon mode with `--restart=always`, so the server will stick even across server restarts.

Links
-----

* [nginx](http://nginx.org/)
* [nginx-rtmp-module](https://github.com/arut/nginx-rtmp-module)
* [ffmpeg](https://www.ffmpeg.org/)
* [OBS](https://obsproject.com/)
* [nginx-rtmp-dockerfile](https://github.com/brocaar/nginx-rtmp-dockerfile)
