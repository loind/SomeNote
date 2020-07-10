# file req.conf

```
[req]
distinguished_name = mobio
x509_extensions = v3_req
prompt = no
[mobio]
C = VN
ST = HN
L = Hanoi
O = Mobio
OU = VIB
CN = api.mobio.vn
[v3_req]
keyUsage = keyEncipherment, dataEncipherment
extendedKeyUsage = serverAuth
subjectAltName = @alt_names
[alt_names]
DNS.1 = api.mobio.vn
DNS.2 = ip-api.com
DNS.3 = hooks.slack.com
DNS.4 = graph.facebook.com
DNS.5 = graph-video.facebook.com
DNS.6 = openapi.zaloapp.com
DNS.7 = openapi.zalo.me
DNS.8 = api.instagram.com
DNS.9 = accounts.google.com
DNS.10 = googleapis.com
DNS.11 = api.line.me
DNS.12 = aet.mobio.vn
```

## Shell command

```
openssl req -x509 -nodes -days 730 -newkey rsa:2048 -keyout private.key -out cert.pem -config req.conf -extensions 'v3_req'
```

```
export SSL_CERT_FILE=/path/cert.pem
```