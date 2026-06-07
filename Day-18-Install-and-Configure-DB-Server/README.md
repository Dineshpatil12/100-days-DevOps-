# Day 18 - Install and Configure MariaDB Server

## Project Overview

This task involved setting up a MariaDB database server on the Nautilus DB Server in the Stratos Datacenter. The objective was to install and configure MariaDB, create a database, create a dedicated database user, and grant appropriate permissions.

---

## Task Requirements

- Install and configure MariaDB Server.
- Create a database named `kodekloud_db9`.
- Create a user named `kodekloud_top`.
- Set the password for the user to `YchZHRcLkL`.
- Grant full privileges on `kodekloud_db9` to `kodekloud_top`.

---

## Implementation Steps

### 1. Install MariaDB Server

```bash
yum install -y mariadb-server
```

### 2. Start and Enable MariaDB Service

```bash
systemctl start mariadb
systemctl enable mariadb
```

### 3. Access MariaDB

```bash
mysql
```

### 4. Create Database

```sql
CREATE DATABASE kodekloud_db9;
```

### 5. Create User

```sql
CREATE USER 'kodekloud_top'@'localhost' IDENTIFIED BY 'YchZHRcLkL';
```

### 6. Grant Database Privileges

```sql
GRANT ALL PRIVILEGES ON kodekloud_db9.* TO 'kodekloud_top'@'localhost';
FLUSH PRIVILEGES;
```

### 7. Verify User Permissions

```sql
SHOW GRANTS FOR 'kodekloud_top'@'localhost';
```

---

## Verification Commands

### Check MariaDB Service Status

```bash
systemctl status mariadb
```

### Verify Database Creation

```sql
SHOW DATABASES;
```

### Verify User Creation

```sql
SELECT User, Host FROM mysql.user;
```

### Verify Granted Permissions

```sql
SHOW GRANTS FOR 'kodekloud_top'@'localhost';
```

---

## Skills Demonstrated

- MariaDB Installation
- Database Administration
- User Management
- Permission Management
- Linux Service Management
- SQL Fundamentals
- Database Security Best Practices

---

## Key Concepts Learned

### MariaDB Server

MariaDB is an open-source Relational Database Management System (RDBMS) that is widely used for storing and managing application data.

### Database

A database is a structured collection of data that can be efficiently stored, retrieved, and managed.

### Database User

Creating dedicated users instead of using the root account improves security and access control.

### Privileges

Database privileges define what actions a user can perform on a database, such as:

- SELECT
- INSERT
- UPDATE
- DELETE
- CREATE
- DROP
- ALTER

Granting privileges on a specific database follows the principle of least privilege.

---

## Outcome

Successfully:

- Installed and configured MariaDB Server.
- Created database `kodekloud_db9`.
- Created user `kodekloud_top`.
- Assigned password authentication.
- Granted full access privileges on `kodekloud_db9`.
- Verified database and user configuration.

---

## Challenge Status

✅ Challenge Completed Successfully

**Reference ID:** `680773fd399a2462b6cc666f`

This exercise provided hands-on experience with MariaDB installation, database creation, user administration, and privilege management in a Linux environment.
