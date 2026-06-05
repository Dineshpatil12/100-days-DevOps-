# Day 16 - Install and Configure Nginx as a Load Balancer

## Objective

Configure Nginx as a Load Balancer to distribute traffic across multiple Apache application servers and improve application availability and performance.

---

## Environment

| Server  | Role                | Port |
| ------- | ------------------- | ---- |
| stlb01  | Nginx Load Balancer | 80   |
| stapp01 | Apache Web Server   | 6300 |
| stapp02 | Apache Web Server   | 6300 |
| stapp03 | Apache Web Server   | 6300 |

---

## Architecture

```text
                 +------------+
                 |   Nginx    |
Users ---------->|  stlb01    |
                 +------------+
                  /    |    \
                 /     |     \
                /      |      \
               /       |       \
      stapp01  stapp02  stapp03
      Apache   Apache   Apache
      :6300    :6300    :6300
```

---

## Steps Performed

### 1. Verified Apache Service

```bash
systemctl status httpd
```

### 2. Checked Apache Listening Port

```bash
ss -tlnp | grep httpd
```

Output:

```text
*:6300
```

### 3. Configured Nginx Upstream Servers

```nginx
upstream app_servers {
    server stapp01:6300;
    server stapp02:6300;
    server stapp03:6300;
}
```

### 4. Configured Reverse Proxy

```nginx
server {
    listen 80;

    location / {
        proxy_pass http://app_servers;
    }
}
```

### 5. Validated Configuration

```bash
nginx -t
```

### 6. Restarted Nginx

```bash
systemctl restart nginx
```

### 7. Tested Connectivity

```bash
curl http://stapp01:6300
curl http://stapp02:6300
curl http://stapp03:6300
```

### 8. Tested Load Balancer

```bash
curl http://stlb01
```

---

## Key Concepts Learned

* Nginx Load Balancer
* Reverse Proxy
* Upstream Server Groups
* Round Robin Load Balancing
* Apache Backend Servers
* Nginx Configuration Validation
* High Availability Architecture

---

## Outcome

Successfully configured Nginx as a load balancer and distributed client requests across three Apache backend servers while maintaining the existing Apache port configuration.

