# rancher-ssl
Fires up Rancher and NGINX with Docker and has NGINX listen with an ssl reverse-proxy for Rancher traffic.

## Run these command on the Rancher server host to create a self-signed SSL cert:
sudo mkdir -p /usr/local/etc/nginx/ssl

cd /usr/local/etc/nginx/ssl

sudo openssl req -x509 -newkey rsa:4096 -keyout rancher-encrypted.key -out rancher.crt -days 365

sudo openssl rsa -in rancher-encrypted.key -out rancher.key

## Run these commands on the host to start up Rancher and NGINX and have NGINX listen on port 443 with https

cd

git clone https://github.com/polinchw/rancher-ssl.git

cd rancher-ssl

docker-compose build

docker-compose up -d

## Rancher Server Access

Point your browser to the public IP of the Rancher server and the Rancher UI will come up.

https://public-ip

![alt text](https://raw.githubusercontent.com/polinchw/rancher-ssl/master/images/rancher-startup.JPG)

## Rancher Access Control

Once your Rancher Server is up and running you should set up a means of authentication so that only you can access the service.

![alt text](https://raw.githubusercontent.com/polinchw/rancher-ssl/master/images/rancher-admin.JPG)
