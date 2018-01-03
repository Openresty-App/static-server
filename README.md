# OpenResty App 

Let's complete a quick hands-on exercise to install OpenResty App on your machine.

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
[root@localhost static-server]# curl -i http://127.0.0.1:10085/
HTTP/1.1 200 OK
Server: openresty/1.13.6.1
Date: Fri, 08 Dec 2017 22:23:13 GMT
Content-Type: text/plain
Transfer-Encoding: chunked
Connection: keep-alive

User-agent: *\nDisallow: /
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
