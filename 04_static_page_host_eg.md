## Create a New Nginx Site Configuration

```bash
nano /etc/nginx/sites-available/staticsite
```

## Add the Nginx Server Block Configuration

```bash
server {
    listen 80;
    listen [::]:80;

    server_name static.balibabu.duckdns.org;

    root /var/www/staticsite;
    index index.html;

    location / {
        try_files $uri $uri/ =404;
    }
}
```

## Enable the Site Configuration

```bash
ln -s /etc/nginx/sites-available/staticsite /etc/nginx/sites-enabled/
```

## Test the Nginx Configuration

```bash
nginx -t
```

## Reload Nginx

```bash
nginx -s reload
```

## Generate an SSL Certificate with Certbot

```bash
certbot --nginx -d static.balibabu.duckdns.org
```

## Expand the Existing Certificate for Multiple Websites

```bash
certbot --nginx --expand -d static.balibabu.duckdns.org -d blog.balibabu.duckdns.org
```
