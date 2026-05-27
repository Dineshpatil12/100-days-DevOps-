# Day 08 - Install and Configure Ansible

## 📌 Task

The Nautilus DevOps team decided to use Ansible for automation and configuration management.

The requirement was to:

- Install Ansible version `4.8.0`
- Use `pip3` only
- Configure Ansible globally so all users can run Ansible commands

---

## 🛠️ Steps Performed

### 1. Checked Python and pip3

```bash
python3 --version
pip3 --version


# Installed Ansible 4.8.0 using pip3

sudo pip3 install ansible==4.8.0

# Verified Installation 

ansible --version
output - ansible [core 2.11.12]

# Verified Global Binary Path

which ansible
output - /usr/local/bin/ansible
