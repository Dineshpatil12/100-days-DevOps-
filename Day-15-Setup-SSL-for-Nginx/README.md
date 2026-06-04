# Day 15: Setup SSL for Nginx

## Objective
Install and configure Nginx with SSL on App Server 3 using a self-signed certificate and verify secure HTTPS access.

---

## Task Requirements

1. Install and configure Nginx on App Server 3.
2. Move the SSL certificate and key from:
   - `/tmp/nautilus.crt`
   - `/tmp/nautilus.key`
3. Configure Nginx to use the SSL certificate and key.
4. Create an `index.html` file with the content:

   Welcome!

5. Verify HTTPS access using curl from the jump host.

---

## Installation

### Install Nginx

```bash
sudo yum install -y nginx
sudo systemctl enable nginx
sudo systemctl start nginx
