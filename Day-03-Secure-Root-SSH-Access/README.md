# Day 03 - Secure Root SSH Access

## Objective
Improve Linux server security by disabling direct root SSH login.

## Commands Used

```bash
vi /etc/ssh/sshd_config
systemctl restart sshd
grep PermitRootLogin /etc/ssh/sshd_config
```

## Configuration

```bash
PermitRootLogin no
```

## Learning Outcome

Learned SSH hardening techniques and root login security configuration.
