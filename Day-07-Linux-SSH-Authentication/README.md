# Day 07 - Linux SSH Authentication (Password-less Login)

## 🎯 Objective
Configure password-less SSH authentication from jump host user `thor` to multiple app servers using SSH keys.

---

## 🖥️ Servers Mapping

| App Server | Username |
|------------|----------|
| stapp01    | tony     |
| stapp02    | steve    |
| stapp03    | banner   |

---

## ⚙️ Steps Performed

### 1. SSH Key Generation on Jump Host

```bash
ssh-keygen
