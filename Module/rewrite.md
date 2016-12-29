# rewrite

## Host Jump

``http://xx.com/oo/?a=1&b=2`` => ``http://admin.xx.com/oo/?a=1&b=2``

```nginx
server {
    listen      80;
    server_name .xx.com;

    charset     utf-8;
    client_max_body_size 75M;

    location /oo {
        rewrite ^(.*)$  $scheme://admin.$host$1;
    }
}
```

