# HTTP => HTTPS

## rewrite

```nginx
server {
    listen  80;
    server_name .xxx.com;
    rewrite ^(.*)$  https://$host$1 permanent;
}
```

