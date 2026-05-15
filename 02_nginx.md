### Now we install tmux and python and others to test this ubuntu
tmux helps to run any service in background even if we exit from the adb shell, without for eg: python server stop as soon as we exit ubuntu
```bash
apt install -y python3 wget tmux nano
```
*you can check tmux cmd https://1-blog.github.io/tmux/*
### Now For hosting on https with nginx, certbot and duckdns

```bash
apt install nginx certbot python3-certbot-nginx
```
```bash
python3 -m http.server 8080 --bind ::
```
```bash
sudo nano /etc/nginx/sites-available/duckdns
```
```bash
server {
    # Listen on IPv6 port 80
    listen [::]:80;
    
    # (Optional) Listen on IPv4 port 80 as well
    listen 80; 

    server_name balibabu.duckdns.org;

    location / {
        # Proxy traffic to your local Python server on IPv6
        proxy_pass http://[::1]:8080;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
    }
}
```

Enable the configuration by linking it to the sites-enabled directory:
```bash
ln -s /etc/nginx/sites-available/duckdns /etc/nginx/sites-enabled/
```
test your configuration
```bash
nginx -t
```
reload the nginx
```bash
nginx -s reload
```
```bash
certbot --nginx -d balibabu.duckdns.org
```
Nginx successfully passes but `http.server` fails to read the directory (e.g., due to permissions in the chroot)
```bash
nano /etc/nginx/nginx.conf
```
*change the 1st line [user www-data;] to [user root;]*

reload the nginx
```bash
nginx -s reload
```
