# Day XX - Website Backup Automation Using Bash Script

## Task

Created a bash script to automate website backup and archive transfer between servers.

## Script Name

```bash
/scripts/ecommerce_archive.sh
```

## What the Script Does

* Creates ZIP archive of website files
* Stores archive in local `/archives` directory
* Copies archive to Nautilus Storage Server
* Uses password-less SSH authentication

## Commands Used

```bash
yum install zip -y
ssh-keygen
ssh-copy-id natasha@ststor01
chmod +x /scripts/ecommerce_archive.sh
scp
zip -r
```

## Verification

Verified archive creation and successful transfer on both App Server and Storage Server.

