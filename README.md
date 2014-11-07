# Docker auto-sub bootstrap bill

This is a Dockerfile to setup https://code.google.com/p/autosub-bootstrapbill/


Build from docker file
```bash
$ git clone https://github.com/WilcoE/auto-sub.git
$ cd auto-sub
$ docker build -t auto-sub .
```

You can also obtain it via:
```bash
docker pull wilcoe/auto-sub
```


---
Instructions to run:

/tv is location of your tvseries

```
$ docker run -d --name="auto-sub" -v /storage/media/tvseries:/tv -p 8083:8083 auto-sub
```


Start the docker instance and it will stay as a daemon and listen on port 8083.

Browse to: ```http://*ipaddress*:8083``` 
