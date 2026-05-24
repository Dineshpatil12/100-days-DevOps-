# Day 02 - Temporary User Setup with Expiry

## Objective
Create a temporary Linux user account with an expiry date.

## Commands Used

```bash
useradd -e 2027-04-15 james
chage -l james
```

## Key Concept

Temporary accounts automatically expire after a specified date for better security and access management.

## Learning Outcome

Learned user expiry management using useradd and chage commands.
