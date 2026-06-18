# Day 24 - Git Create Branches

## Objective
Create a new Git branch from the master branch without modifying any source code.

## Environment
- Server: Storage Server (ststor01)
- Repository: /usr/src/kodekloudrepos/news

## Steps Performed

### Navigate to Repository
```bash
cd /usr/src/kodekloudrepos/news
```

### Switch to Master Branch
```bash
git checkout master
```

### Create New Branch
```bash
git checkout -b xfusioncorp_news
```

### Verify Branch
```bash
git branch
```

## Result

Successfully created a new branch:

```text
xfusioncorp_news
```

from the `master` branch.

## Git Commands Used

| Command | Purpose |
|----------|----------|
| `git checkout master` | Switch to master branch |
| `git checkout -b xfusioncorp_news` | Create and switch to new branch |
| `git branch` | List all branches |

## Key Learning

- Branches allow isolated development.
- New features can be developed without affecting the main branch.
- `git checkout -b <branch-name>` creates and switches to a branch in one command.

## Status

✅ Challenge Completed Successfully
