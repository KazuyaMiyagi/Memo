# OpenSSL

```
openssl s_client -connect example.com:443 -showcerts < /dev/null | openssl x509 -inform PEM -text -out /etc/pki/tls/certs/localhost.crt ;
curl -v --cacert /etc/pki/tls/certs/localhost.crt -X POST https://example.com
```

```
openssl s_client -connect example.com:443 -showcerts < /dev/null | openssl x509 -inform PEM -text -out /etc/pki/tls/certs/localhost.crt
curl -v --cacert /etc/pki/tls/certs/localhost.crt -X POST https://example.com
curl -v -X POST http://example.com
```
