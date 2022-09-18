# WordPress NextJS deployment


## Prepare


### 1. Config Nginx
```sh
sed -i 's/${SITE_DOMAIN}/domain.ru/g' nginx/conf/nginx.conf
```
### 2. Create Certs
```sh
docker compose up -d --rm certnginx
docker compose run --rm certbot certonly --webroot --webroot-path /var/www/certbot -d domain.ru
```
### 3. Test run
### 4. Upload media to ./wordpress/wp-content/uploads
### 5. Upload plugins to ./wordpress/wp-content/plugins
### 6. Clone WP theme to ./wordpress/wp-content/themes
### 7. Clone NextJS app to ./nextjs
### 8. Upload database to dump.sql
### 9. Run
### 10. Config certs renewal
```sh
docker compose run --rm certbot renew
```