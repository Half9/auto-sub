# Docker auto-sub bootstrap bill

This is a Dockerfile to setup https://code.google.com/p/autosub-bootstrapbill/


Build from docker file
```
$ git clone https://github.com/WilcoE/auto-sub.git
$ cd auto-sub
$ docker build -t wilcoe/auto-sub .
```


You can also obtain it with:
```
docker pull wilcoe/auto-sub
```


---
# Instructions to run:

/storage/media/tvseriers is the location of your tvseries on your server

```
$ docker run -d --name="auto-sub" -v /storage/media/tvseries:/tv -p 8083:8083 wilcoe/auto-sub
```

Start the docker instance and it will stay as a daemon and listen on port 8083.

Browse to: ```http://*ipaddress*:8083```

When you get: Something went wrong when traversing directory
Then check with:

```
find /storage/media/tvseries | perl -ne 'print if /[^[:ascii:]]/'
```
And rename files which are showing up


---
to access the container please use
```
docker exec -it container_id /bin/bash
```
