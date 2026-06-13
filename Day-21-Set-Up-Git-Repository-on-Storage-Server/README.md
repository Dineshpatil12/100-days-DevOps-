# Day 21: Set Up Git Repository on Storage Server

## Objective

Install Git on the Storage Server and create a bare Git repository for the Nautilus development team.

## Task Requirements

* Install the Git package using yum.
* Create a bare Git repository named `/opt/ecommerce.git`.

## Environment

* Server: Storage Server (`ststor01`)
* Operating System: CentOS Stream 9

## Commands Used

### Install Git

```bash
yum install -y git
```

### Verify Git Installation

```bash
git --version
```

### Create Bare Repository

```bash
git init --bare /opt/ecommerce.git
```

### Verify Bare Repository

```bash
git --git-dir=/opt/ecommerce.git rev-parse --is-bare-repository
```

Expected Output:

```text
true
```

## Repository Structure

```text
/opt/ecommerce.git
├── HEAD
├── config
├── description
├── hooks/
├── info/
├── objects/
└── refs/
```

## Outcome

* Git was successfully installed.
* Bare repository `/opt/ecommerce.git` was successfully created.
* Repository verification confirmed it is a bare Git repository.

## Status

Task completed successfully.

