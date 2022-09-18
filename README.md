# WordPress NextJS deployment


## Prepare


### 1. Config Nginx
```sh
sed -i 's/${SITE_DOMAIN}/domain.ru/g' nginx/conf/nginx.conf
```
### 2. Create Certs
```sh
docker compose up -d certnginx
docker compose run --rm certbot certonly --webroot --webroot-path /var/www/certbot -d domain.ru
```
### 3. Config certs renewal
```sh
docker compose run --rm certbot renew
```