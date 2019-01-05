# Data scraping

## Proxy

### Tor

1. [tor-privoxy-alpine](https://github.com/rdsubhas/docker-tor-privoxy-alpine)


The smallest (15 MB) docker image with Tor and Privoxy on Alpine Linux.

```
docker pull rdsubhas/tor-privoxy-alpine
docker run -d -p 8118:8118 -p 9050:9050 rdsubhas/tor-privoxy-alpine
curl --proxy localhost:8118 https://www.google.com

```

2. [Mattes docker-rotating-proxy](https://github.com/mattes/rotating-proxy)

Use :

```
# build docker container
docker build -t mattes/rotating-proxy:latest .

# ... or pull docker container
docker pull mattes/rotating-proxy:latest

# start docker container
docker run -d -p 5566:5566 -p 4444:4444 --env tors=25 mattes/rotating-proxy

# test with ...
curl --proxy 127.0.0.1:5566 http://echoip.com
curl --proxy 127.0.0.1:5566 http://header.jsontest.com

# monitor
http://127.0.0.1:4444/haproxy?stats

```
