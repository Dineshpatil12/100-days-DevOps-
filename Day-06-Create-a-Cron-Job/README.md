# Day 6 - Create a Cron Job

## Objective

Configure and test automated cron job scheduling on Linux servers.

---

## Task Overview

Configured and verified cron job automation on all Nautilus application servers in the Stratos Datacenter environment.

---

## Servers Configured

- stapp01
- stapp02
- stapp03

---

## Work Completed

### 1. Installed Cron Package

Installed the `cronie` package to enable cron scheduling support.

### Command Used

```bash
yum install -y cronie
```

---

### 2. Started and Enabled Cron Service

Started the cron daemon and enabled automatic startup after reboot.

### Commands Used

```bash
systemctl start crond
systemctl enable crond
```

---

### 3. Configured Root Cron Job

Added a cron job for the root user.

### Command Used

```bash
crontab -e
```

### Cron Entry

```bash
*/5 * * * * echo hello > /tmp/cron_text
```

---

## Cron Schedule Explanation

| Field | Meaning |
|------|------|
| */5 | Every 5 minutes |
| * | Every hour |
| * | Every day |
| * | Every month |
| * | Every weekday |

---

## Command Executed by Cron

```bash
echo hello > /tmp/cron_text
```

This command creates or updates the file:

```bash
/tmp/cron_text
```

with the value:

```text
hello
```

---

## Verification Performed

### Verified Cron Service Status

```bash
systemctl status crond
```

### Result

- Cron service was active and running successfully.

---

### Verified Cron Job Entry

```bash
crontab -l
```

### Result

- Correct cron job entry was present for the root user.

---

### Verified Cron Job Execution

```bash
cat /tmp/cron_text
```

### Output

```text
hello
```

This confirmed successful cron execution.

---

## Skills Practiced

- Linux cron scheduling
- Cron service management
- Root crontab configuration
- Linux automation basics
- Service verification and troubleshooting

---

## Real-World Relevance

Cron jobs are widely used in production Linux environments for:

- Automated backups
- Log cleanup
- Monitoring scripts
- Scheduled deployments
- System maintenance tasks
- Health checks

Understanding cron scheduling is an essential Linux and DevOps skill.
