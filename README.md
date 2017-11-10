# rancher-ssl
Just a simple project that fires up Rancher and NGINX with SSL.

## Run this command on the host:
sudo openssl req -x509 -newkey rsa:2048 -keyout rancher.key -out rancher.crt -days 365
