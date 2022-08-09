## adadguard home docker compose

```lang-docker
version: "2"
services:
   adguardhome:
     image: adguard/adguardhome
     container_name: adguardhome
     ports:
       - 53:53/tcp
       - 53:53/udp
       - 784:784/udp
       - 853:853/tcp
       - 3000:3000/tcp
       - 88:80/tcp
     volumes:
       - ./work:/opt/adguardhome/work
       - ./conf:/opt/adguardhome/conf
```

## add certificate localhost

```bash
openssl req -x509 -out localhost.crt -keyout localhost.key \
  -newkey rsa:2048 -nodes -sha256 \
  -subj '/CN=localhost' -extensions EXT -config <( \
   printf "[dn]\nCN=localhost\n[req]\ndistinguished_name = dn\n[EXT]\nsubjectAltName=DNS:localhost\nkeyUsage=digitalSignature\nextendedKeyUsage=serverAuth")
```
## VIDEO

[![INSATALL ADDGUARD HOME](https://i9.ytimg.com/vi_webp/A4FTz2vLCMo/mqdefault.webp?v=62f24f4f&sqp=CJidyZcG&rs=AOn4CLAwkveAQ-AKQXrCEDGJIff7NIaMrw)](https://youtu.be/A4FTz2vLCMo)
