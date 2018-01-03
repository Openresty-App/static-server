# OpenResty App 

Serving static content

## Depend

* [OpenResty](http://openresty.org/en/installation.html)

## Run

```
git clone https://github.com/Openresty-App/static-server.git
cd static-server

./scripts/startup.sh
./scripts/reload.sh
./scripts/stop.sh
```

## Test

```lang=shell
[root@vagrant static-server]# curl -i http://127.0.0.1:10085/robots.txt
HTTP/1.1 200 OK
Server: openresty/1.11.2.4
Date: Wed, 03 Jan 2018 09:33:37 GMT
Content-Type: text/plain
Content-Length: 25
Connection: keep-alive

User-agent: *
Disallow: /
```

# nginx-app.conf

```lang=nginx
# app

server {
    listen       10085;
    server_name  localhost;
    root /root/resthub-console/f2e/vue-element-admin/dist/static;

    location = /robots.txt {
        return 200 'User-agent: *\nDisallow: /';
    }
}
```
