# httpbin in a docker over cloudflared 

## Settting up

* Deploy httpbin docker images on a Docker environment: 
```
docker pull kennethreitz/httpbin
```
* List docker images: 
```
docker images
```
* Run docker image: (-p  host_port:container_port)
```
docker run -d=true -p 80:80 kennethreitz/httpbin
```

* List docker containers: 
```
docker ps -a
```


* Download `cloudflared`: 
```
wget https://bin.equinox.io/c/VdrWdbjqyF/cloudflared-stable-linux-amd64.deb
dpkg -i cloudflared-stable-linux-amd64.deb
cloudflared --version
cloudflared login
```

* Run `cloudflared` one-off
```
cloudflared --config ~/httpbin-cloudflared/config.yml
```

* Run `cloudflared` as a service

```
ln -s ~/httpbin-cloudflared/config.yml /etc/cloudflared/config.yml
scloudflared service install
service cloudflared start
```

## TODO
* Expose /metrics 


## References
* [httpbin on Dockerhub](https://hub.docker.com/r/kennethreitz/httpbin/)
* [Developers docs for Argo Tunnel aka `cloudflared`](https://developers.cloudflare.com/argo-tunnel/downloads/)