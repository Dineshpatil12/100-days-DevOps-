# Day 09 - Fix MariaDB Service Issue

## Task

The Nautilus application was unable to connect to the database because the MariaDB service was down on the database server.

## Issue Found

MariaDB service failed to start due to permission issues on:

```bash
/run/mariadb/mariadb.pid
```

The `/run/mariadb` directory had incorrect ownership and permissions.

## Fix Applied

### Checked service status

```bash
sudo systemctl status mariadb
```

### Checked logs

```bash
sudo journalctl -xeu mariadb.service
sudo tail -20 /var/log/mariadb/mariadb.log
```

### Fixed permissions

```bash
sudo mkdir -p /run/mariadb
sudo chown -R mysql:mysql /run/mariadb
sudo chmod 755 /run/mariadb
```

### Restarted MariaDB

```bash
sudo systemctl restart mariadb
sudo systemctl status mariadb
```

## Result

MariaDB service started successfully and the application database connectivity issue was resolved.

