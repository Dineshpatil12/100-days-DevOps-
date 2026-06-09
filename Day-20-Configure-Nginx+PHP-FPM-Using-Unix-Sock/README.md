# Day 20: Nginx + PHP-FPM on port 8099 (stapp01 only)

## Task Requirements
- Install nginx on app server 1 (stapp01), port 8099, document root `/var/www/html`
- Install php-fpm 8.1, use unix socket `/var/run/php-fpm/default.sock`
- Configure nginx and php-fpm together
- Test: `curl http://stapp01:8099/index.php` from jump host

## Solution on stapp01

```bash
# Install repos and packages
dnf install -y epel-release
dnf install -y https://rpms.remirepo.net/enterprise/remi-release-9.rpm
dnf module reset php -y
dnf module enable php:remi-8.1 -y
dnf install -y nginx php-fpm

# Configure php-fpm
vi /etc/php-fpm.d/www.conf
# Set:
listen = /var/run/php-fpm/default.sock
listen.owner = nginx
listen.group = nginx
listen.mode = 0660
user = nginx
group = nginx

# Create socket directory
mkdir -p /var/run/php-fpm
chown -R nginx:nginx /var/run/php-fpm

# Configure nginx
cat > /etc/nginx/conf.d/php-app.conf << 'EOF'
server {
    listen 8099;
    server_name stapp01;
    root /var/www/html;
    index index.php index.html;
    location / {
        try_files $uri $uri/ =404;
    }
    location ~ \.php$ {
        include fastcgi_params;
        fastcgi_pass unix:/var/run/php-fpm/default.sock;
        fastcgi_index index.php;
        fastcgi_param SCRIPT_FILENAME $document_root$fastcgi_script_name;
    }
}
EOF

# Optional: disable default site
mv /etc/nginx/conf.d/default.conf /etc/nginx/conf.d/default.conf.bak 2>/dev/null

# Start services
systemctl enable nginx php-fpm
systemctl start php-fpm nginx

# Test locally
curl http://localhost:8099/index.php
