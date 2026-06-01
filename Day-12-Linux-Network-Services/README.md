# Day 12 - Linux Network Services

## Objective

Troubleshoot and restore Apache accessibility on port 3001 on stapp01.

## Issue

Apache was not reachable from the jump host on port 3001.

## Root Cause

* A port conflict existed because `sendmail` was already listening on port `3001`.
* Apache failed to start with:

  ```
  Address already in use
  ```
* The firewall was also blocking incoming connections to port `3001`.

## Resolution

### Check Port Usage

```bash
ss -tulpn | grep 3001
```

### Stop Conflicting Service

```bash
systemctl stop sendmail
```

### Start Apache

```bash
systemctl start httpd
```

### Allow Port 3001

```bash
iptables -I INPUT 5 -p tcp --dport 3001 -j ACCEPT
service iptables save
```

### Verify

```bash
curl http://stapp01:3001
```

## Result

Apache started successfully on port 3001 and became accessible from the jump host.

