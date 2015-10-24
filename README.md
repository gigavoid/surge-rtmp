The Surge RTMP streaming server
=====================

Based on brocaar's [nginx-rtmp-module](https://github.com/brocaar/nginx-rtmp-dockerfile)



Running
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
