## ADGUARD HOME DOCKER COMPOSE

```yaml
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

## ADD CERTIFICATE LOCALHOST

```console
openssl req -x509 -out localhost.crt -keyout localhost.key \
  -newkey rsa:2048 -nodes -sha256 \
  -subj '/CN=localhost' -extensions EXT -config <( \
   printf "[dn]\nCN=localhost\n[req]\ndistinguished_name = dn\n[EXT]\nsubjectAltName=DNS:localhost\nkeyUsage=digitalSignature\nextendedKeyUsage=serverAuth")
```
## VIDEO GUIDE

[![INSATALL ZSH](https://i.ytimg.com/vi/A4FTz2vLCMo/maxresdefault.jpg)](https://www.youtube.com/watch?v=A4FTz2vLCMo)
