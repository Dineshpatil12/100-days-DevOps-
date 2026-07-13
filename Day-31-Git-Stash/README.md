# Day 31: Git Stash

## Objective
Learn how to temporarily save uncommitted changes using Git Stash and restore a specific stash.

## Task
- Navigate to the Git repository.
- List all available stashes.
- Restore `stash@{1}`.
- Commit the restored changes.
- Push the changes to the remote repository.

## Commands Used

```bash
cd /usr/src/kodekloudrepos/beta

git stash list

git stash apply stash@{1}

git status

git add .

git commit -m "Restore changes from stash@{1}"

git push origin master
```

## Output

```text
stash@{0}: WIP on master: f0d14fe initial commit
stash@{1}: WIP on master: f0d14fe initial commit

[master 42f4d8f] Restore changes from stash@{1}
1 file changed, 1 insertion(+)
create mode 100644 welcome.txt

To /opt/beta.git
f0d14fe..42f4d8f master -> master
```

## Git Stash Commands

| Command | Description |
|---------|-------------|
| `git stash` | Save uncommitted changes. |
| `git stash list` | Display all stashes. |
| `git stash apply stash@{n}` | Restore a specific stash without removing it. |
| `git stash pop stash@{n}` | Restore a stash and remove it from the stash list. |
| `git stash drop stash@{n}` | Delete a specific stash. |
| `git stash clear` | Delete all stashes. |

## Key Difference

### `git stash apply`
- Restores the stash.
- Keeps the stash in the stash list.

### `git stash pop`
- Restores the stash.
- Removes the stash from the stash list.

## Interview Questions

**1. What is Git Stash?**
> Git Stash temporarily saves uncommitted changes so you can switch branches or work on another task without creating a commit.

**2. How do you view all stashes?**
```bash
git stash list
```

**3. How do you restore a specific stash?**
```bash
git stash apply stash@{1}
```

**4. What is the difference between `git stash apply` and `git stash pop`?**
- `apply` restores the stash and keeps it.
- `pop` restores the stash and removes it.

## Result
Successfully restored `stash@{1}`, committed the changes, and pushed them to the remote repository.

## Status
**Completed Successfully**
