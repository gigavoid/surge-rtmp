The Surge RTMP streaming server
=====================

Based on brocaar's [https://github.com/brocaar/nginx-rtmp-dockerfile](nginx-rtmp-module).


Running
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
