# Day 01 - Linux User Setup with Non-Interactive Shell

## Objective
Create a Linux user with disabled interactive login access.

## Commands Used

```bash
sudo useradd -m -s /sbin/nologin javed
id javed
grep javed /etc/passwd
```

## Key Concept

Non-interactive shells prevent direct user login while still allowing the account to exist for services or automation tasks.

## Learning Outcome

Learned Linux user creation and secure shell restriction using nologin.
