# Basics
create a new user:
```
adduser demo
```

Sudo permission for new user
```
gpasswd -a demo sudo
```

Restrict root login, restart SSH
```
nano /etc/ssh/sshd_config
service ssh restart
```

Start firewall, allowing port 25, 80, 443, enable it
```
sudo ufw allow ssh
sudo ufw allow 80/tcp
sudo ufw allow 25/tcp
sudo ufw allow 443/tcp
sudo ufw enable
```

update/upgrade
```
sudo apt-get update
sudo apt-get upgrade
```

Set Timezone
```
sudo dpkg-reconfigure tzdata
```

Sync time with NTP
```
sudo apt-get install ntp
```

# Install Let's Encrypt (ubuntu 14)
```
cd /usr/local/sbin
sudo wget https://dl.eff.org/certbot-auto
sudo chmod a+x /usr/local/sbin/certbot-auto
```

Going to modify the location mapping:

`sudo nano /etc/nginx/sites-available/default`

Add this to your `server` block:

```
location ~ /.well-known {
    allow all;
}
```

check for nginx syntax errors, then restart:
```
sudo nginx -t
sudo service nginx restart
```

Time to have certbot do its thing:

`certbot-auto certonly -a webroot --webroot-path=/usr/share/nginx/html -d example.com -d www.example.com`

Generate Strong Diffie-Hellman Group:

`sudo openssl dhparam -out /etc/ssl/certs/dhparam.pem 2048`

Comment out some lines in this file: `sudo nano /etc/nginx/sites-available/default`

```
listen 80 default_server;
        listen [::]:80 default_server ipv6only=on;
```

Add these to the server block:
```
listen 443 ssl;

        server_name example.com www.example.com;

        ssl_certificate /etc/letsencrypt/live/example.com/fullchain.pem;
        ssl_certificate_key /etc/letsencrypt/live/example.com/privkey.pem;

         ssl_protocols TLSv1 TLSv1.1 TLSv1.2;
        ssl_prefer_server_ciphers on;
        ssl_dhparam /etc/ssl/certs/dhparam.pem;
        ssl_ciphers 'ECDHE-RSA-AES128-GCM-SHA256:ECDHE-ECDSA-AES128-GCM-SHA256:ECDHE-RSA-AES256-GCM-SHA384:ECDHE-ECDSA-AES256-GCM-SHA384:DHE-RSA-AES128-GCM-SHA256:DHE-DSS-AES128-GCM-SHA256:kEDH+AESGCM:ECDHE-RSA-AES128-SHA256:ECDHE-ECDSA-AES128-SHA256:ECDHE-RSA-AES128-SHA:ECDHE-ECDSA-AES128-SHA:ECDHE-RSA-AES256-SHA384:ECDHE-ECDSA-AES256-SHA384:ECDHE-RSA-AES256-SHA:ECDHE-ECDSA-AES256-SHA:DHE-RSA-AES128-SHA256:DHE-RSA-AES128-SHA:DHE-DSS-AES128-SHA256:DHE-RSA-AES256-SHA256:DHE-DSS-AES256-SHA:DHE-RSA-AES256-SHA:AES128-GCM-SHA256:AES256-GCM-SHA384:AES128-SHA256:AES256-SHA256:AES128-SHA:AES256-SHA:AES:CAMELLIA:DES-CBC3-SHA:!aNULL:!eNULL:!EXPORT:!DES:!RC4:!MD5:!PSK:!aECDH:!EDH-DSS-DES-CBC3-SHA:!EDH-RSA-DES-CBC3-SHA:!KRB5-DES-CBC3-SHA';
        ssl_session_timeout 1d;
        ssl_session_cache shared:SSL:50m;
        ssl_stapling on;
        ssl_stapling_verify on;
        add_header Strict-Transport-Security max-age=15768000;
```

New server block:
```
server {
    listen 80;
    server_name example.com www.example.com;
    return 301 https://$host$request_uri;
}
```

Restart nginx: `sudo service nginx restart`

# Setup Auto Renewal

This renews it every Monday at 2:30 am, and reload Nginx at 2:35am
```
certbot-auto renew
sudo crontab -e
30 2 * * 1 /usr/local/sbin/certbot-auto renew >> /var/log/le-renew.log
35 2 * * 1 /etc/init.d/nginx reload
```