# Secure Sockets Layer(SSL)

```nginx
server {
    listen       443 ssl;
    # listen       443 default_server ssl;
    server_name  .xxx.com;
    charset      utf-8;

    ssl on;
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

## [StartSSL](https://www.startssl.com)

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

*Tips: Firefox can not open*

## [Let's Encrypt](https://letsencrypt.org/)

* [acme-tiny - A tiny script to issue and renew TLS certs from Let's Encrypt](https://github.com/diafygi/acme-tiny)

* [certbot - Automatically enable HTTPS on your website with EFF's Certbot, deploying Let's Encrypt certificates.](https://certbot.eff.org/)

  * Stuck @ ``Installing Python packages...`` in China. You should change pip source first.

    * [no response "Installing Python packages" #2516](https://github.com/certbot/certbot/issues/2516)
    * vim `~/.pip/pip.conf`

      ```
      [global]
      index-url = http://mirrors.aliyun.com/pypi/simple/

      [install]
      trusted-host=mirrors.aliyun.com
      ```
