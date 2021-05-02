# cloud-server
- [cloud-server](#cloud-server)
  - [Nginx setup](#nginx-setup)
  - [Firewall setup with UFW](#firewall-setup-with-ufw)
  - [HTTPS setup](#https-setup)
  - [Cloud VSCode](#cloud-vscode)
    - [Clang for CPP](#clang-for-cpp)

## Nginx setup

[How To Install Nginx on Ubuntu from DigitalOcean](https://www.digitalocean.com/community/tutorials/how-to-install-nginx-on-ubuntu-20-04)

## Firewall setup with UFW

[Tutorial from DigitalOcean](https://www.digitalocean.com/community/tutorials/how-to-setup-a-firewall-with-ufw-on-an-ubuntu-and-debian-cloud-server)

**Note**:
- Usually UFW is not enabled by default. So after enabling UFW, make sure you allow ssh connection immediate: `sudo ufw allow ssh`.

## HTTPS setup

Get TLS certificate from [Let's Encrypt](https://letsencrypt.org/).

## Cloud VSCode

Remote VSCode editor and development environment. Following this [instruction](https://github.com/cdr/code-server/blob/main/docs/guide.md) for setup.

I recommend to set up using `Nginx` with sub-domain and `HTTPS`:

```
server {
    listen 80;
    listen [::]:80;
    server_name sub.mydomain.com; # use sub-domain instead

    location / {
      proxy_pass http://localhost:8080/;
      proxy_set_header Host $host;
      proxy_set_header Upgrade $http_upgrade;
      proxy_set_header Connection upgrade;
      proxy_set_header Accept-Encoding gzip;
    }
}
```

### Clang for CPP

- install clang-11 (with lldb and lld):

```bash
# To retrieve the archive signature:
wget -O - https://apt.llvm.org/llvm-snapshot.gpg.key|sudo apt-key add -
# Fingerprint: 6084 F3CF 814B 57C1 CF12 EFD5 15CF 4D18 AF4F 7421

# To install just clang, lld and lldb (11 release):
apt-get install clang-11 lldb-11 lld-11
```

ref: https://apt.llvm.org/

- compile single cpp file:

```bash
clang++ -Wall -std=c++17 test.cc -o test
```
