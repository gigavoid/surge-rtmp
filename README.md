The Surge RTMP streaming server
=====================

Based on brocaar's [https://github.com/brocaar/nginx-rtmp-dockerfile](nginx-rtmp-module).



Running
------
If you want to run the server by first building it, please see the Building section below.

There are automated builds for this project at our (https://hub.docker.com/r/gigavoid/surge-rtmp)[Docker Hub], which can be run without even cloning this repository. For example:

```
docker run --restart=always --name surge-rtmp -p 1936:80 -p 1935:1935 -d gigavoid/surge-rtmp
```


Building
-------
There are two scripts in the `bin` folder that either can be used as is or modified to use settings that match your setings (such as ports).

`run-foreground` is great for development - it runs the script blocking and a `CTRL-c` is enough to quit it.

`run-background` will put the server in a daemon mode with `--restart=always`, so the server will stick even across server restarts.

Links
-----

* http://nginx.org/
* https://github.com/arut/nginx-rtmp-module
* https://www.ffmpeg.org/
* https://obsproject.com/
* https://github.com/brocaar/nginx-rtmp-dockerfile
