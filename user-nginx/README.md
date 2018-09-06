#refer to
https://github.com/smebberson/docker-alpine/tree/master/examples/user-nginx

#your own server config
```
$ cat /etc/nginx/conf.d/default.conf
server {
    listen 80;
    server_name "";

    root /usr/html;
    index index.html;

    location /favicon.ico {
        log_not_found off;
    }
}
```
change Dockerfile to replace your my.conf to flask.conf

#use docker-compose
```
version: '3.2'

services:

  nginx:
    restart: always
    build: ./user-nginx/
    ports:
      - "80:80"
    networks:
      - web

networks:
  web:
    external: true
```
