# Day 14 - Linux Process Troubleshooting

## Issue
Apache service failed to start because port 5002 was already occupied by sendmail.

## Troubleshooting Steps
- Checked Apache service status.
- Found "Address already in use" error.
- Verified port usage with:
  ss -tulpn | grep 5002
- Identified sendmail using port 5002.
- Stopped sendmail service.
- Started Apache service.
- Verified Apache was running and listening on port 5002.

## Verification

systemctl status httpd
ss -tulpn | grep 5002

Result: Apache service is running successfully on port 5002.
