# Day 17: Install and Configure PostgreSQL

## Objective

Configure a PostgreSQL database server for a new application deployment by creating a database user, creating a database, and granting the required permissions.

---

## Task Requirements

The Nautilus application development team requested the following PostgreSQL configuration:

1. Create a PostgreSQL user:

   * Username: `kodekloud_roy`
   * Password: `B4zNgHA7Ya`

2. Create a database:

   * Database Name: `kodekloud_db10`

3. Grant full privileges on the database to the user.

> Note: PostgreSQL service restart was not required.

---

## Environment

| Component       | Details        |
| --------------- | -------------- |
| Database Server | PostgreSQL     |
| Database Name   | kodekloud_db10 |
| User Name       | kodekloud_roy  |
| Privileges      | Full Access    |

---

## Implementation Steps

### Connect to PostgreSQL

```bash
sudo -u postgres psql
```

### Create Database User

```sql
CREATE USER kodekloud_roy WITH PASSWORD 'B4zNgHA7Ya';
```

### Create Database

```sql
CREATE DATABASE kodekloud_db10;
```

### Grant Permissions

```sql
GRANT ALL PRIVILEGES ON DATABASE kodekloud_db10 TO kodekloud_roy;
```

---

## Verification

### List PostgreSQL Users

```sql
\du
```

Expected Output:

```text
kodekloud_roy
postgres
```

### List Databases

```sql
\l
```

Expected Output:

```text
kodekloud_db10
```

---

## Skills Practiced

* PostgreSQL Administration
* Database User Management
* Database Creation
* Permission Management
* SQL Commands
* Linux System Administration

---

## Commands Used

```bash
sudo -u postgres psql
```

```sql
CREATE USER kodekloud_roy WITH PASSWORD 'B4zNgHA7Ya';
CREATE DATABASE kodekloud_db10;
GRANT ALL PRIVILEGES ON DATABASE kodekloud_db10 TO kodekloud_roy;
```

---

## Key Learnings

* Created PostgreSQL users and assigned passwords.
* Created a dedicated database for an application.
* Granted database-level privileges to an application user.
* Verified database objects using PostgreSQL administrative commands.
* Learned that user and privilege changes take effect immediately without restarting PostgreSQL.

---

## Outcome

Successfully configured PostgreSQL by creating the required user, database, and permissions, making the environment ready for application deployment.

