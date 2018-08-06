# httpbin in a docker over cloudflared 

Deploy httpbin docker images on a Docker environment
`docker pull kennethreitz/httpbin`
List docker images: 
`docker images`
List docker containers:
docker container ls -a
Run docker image:
`docker run -d=true -p 80:8080 kennethreitz/httpbin`
