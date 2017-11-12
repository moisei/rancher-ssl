# rancher-ssl
Just a simple project that fires up Rancher and NGINX with SSL.

## Run these command on the host:
sudo mkdir -p /usr/local/etc/nginx/ssl

cd /usr/local/etc/nginx/ssl

sudo openssl req -x509 -newkey rsa:2048 -keyout rancher-encrypted.key -out rancher.crt -days 365

sudo openssl rsa -in rancher-encrypted.key -out rancher.key
