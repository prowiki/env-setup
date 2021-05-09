# cloud-server
- [cloud-server](#cloud-server)
  - [Nginx setup](#nginx-setup)
  - [Firewall setup with UFW](#firewall-setup-with-ufw)
  - [HTTPS setup](#https-setup)
  - [Cloud VSCode](#cloud-vscode)

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
