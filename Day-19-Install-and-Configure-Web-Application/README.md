# Day 19 - Install and Configure Web Application

## Objective

Configure Apache HTTP Server on App Server 1 to host two static websites:

* News Website: `http://localhost:8088/news/`
* Games Website: `http://localhost:8088/games/`

---

## Environment

| Component  | Details                    |
| ---------- | -------------------------- |
| Web Server | Apache HTTP Server (httpd) |
| Server     | stapp01                    |
| Port       | 8088                       |
| Websites   | News, Games                |

---

## Tasks Performed

### 1. Install Apache HTTP Server

Installed the Apache web server package and required dependencies.

```bash
yum install -y httpd
```

---

### 2. Configure Apache to Listen on Port 8088

Edited the Apache configuration file:

```bash
vi /etc/httpd/conf/httpd.conf
```

Modified:

```apache
Listen 80
```

to:

```apache
Listen 8088
```

---

### 3. Create Website Directories

Created directories for hosting both websites.

```bash
mkdir -p /var/www/html/news
mkdir -p /var/www/html/games
```

---

### 4. Copy Website Content

Copied website backup files from the jump host to the application server.

```bash
cp -r /tmp/news/* /var/www/html/news/
cp -r /tmp/games/* /var/www/html/games/
```

---

### 5. Configure Permissions

Assigned proper ownership and permissions.

```bash
chown -R apache:apache /var/www/html/news
chown -R apache:apache /var/www/html/games

chmod -R 755 /var/www/html/news
chmod -R 755 /var/www/html/games
```

---

### 6. Start and Enable Apache Service

```bash
systemctl enable httpd
systemctl restart httpd
```

---

## Validation

### Verify News Website

```bash
curl http://localhost:8088/news/
```

Output:

```html
<h1>KodeKloud</h1>
<p>This is a sample page for our news website</p>
```

### Verify Games Website

```bash
curl http://localhost:8088/games/
```

Output:

```html
<h1>KodeKloud</h1>
<p>This is a sample page for our games website</p>
```

### Verify Apache Listening on Port 8088

```bash
lsof -i :8088
```

Output:

```text
httpd LISTEN
```

---

## Key Learning Outcomes

* Apache HTTP Server installation and configuration
* Changing default Apache listening port
* Hosting multiple static websites
* Managing web content directories
* Setting Linux file permissions and ownership
* Service management using systemctl
* Website validation using curl

---

## Result

Successfully configured Apache HTTP Server on port **8088** and hosted two static websites:

* News Website
* Games Website

Both applications were verified and accessible through their respective URLs.

