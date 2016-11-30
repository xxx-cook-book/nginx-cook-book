# SSL

```nginx
server {
    listen       443 ssl;
    # listen       443 default_server ssl;
    server_name  .xxx.com;
    charset      utf-8;

    ssl on;
    # [StartSSL](https://www.startssl.com)
    ssl_certificate         /xxx/xxx.crt;
    ssl_certificate_key     /xxx/xxx-privkey.key;
    # ssl_client_certificate  /xxx/xxx.pem;
    ssl_session_timeout     5m;
    keepalive_timeout    70;
    # ssl_verify_client       on;
    ssl_protocols           SSLv2 SSLv3 TLSv1;

    ...
}
```

## StartSSL

* Create ``privkey.key``

  ```shell
  openssl genrsa -out xxx-privkey.key 2048
  ```

* Create ``csr``

  ```shell
  openssl req -new -key xxx-privkey.key -out xxx.csr
  ```

* Certificate

  ```shell
  xxx.crt
  ```

  ​