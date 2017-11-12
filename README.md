# rancher-ssl
Fires up Rancher and NGINX with Docker and has NGINX listen with an ssl reverse-proxy for Rancher traffic.

## Run these command on the host to create an self-signed SSL Cert:
sudo mkdir -p /usr/local/etc/nginx/ssl

cd /usr/local/etc/nginx/ssl

sudo openssl req -x509 -newkey rsa:2048 -keyout rancher-encrypted.key -out rancher.crt -days 365

sudo openssl rsa -in rancher-encrypted.key -out rancher.key

## Run these commands on the host to start up Rancher and NGINX and have NGINX listen on port 443 with https

git clone polinchw/rancher-ssl

cd rancher-ssl

docker-compose build

docker-compose up -d

