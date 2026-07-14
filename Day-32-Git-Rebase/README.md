# Day 32: Git Rebase

## Objective
Rebase the `feature` branch with the latest changes from the `master` branch without creating a merge commit, and push the updated branch to the remote repository.

## Environment
- Repository: `/usr/src/kodekloudrepos/beta`
- Remote Repository: `/opt/beta.git`

## Commands Used

```bash
cd /usr/src/kodekloudrepos/beta

git branch

git checkout feature

git rebase master

git status

git push origin feature --force-with-lease
```

## Verification

```bash
git log --oneline --graph --all --decorate
```

Example Output:

```
* Add new feature
* Update info.txt
* initial commit
```

## What I Learned

- Git Rebase applies feature branch commits on top of the latest master branch.
- Rebase creates a clean and linear commit history.
- Unlike Git Merge, Rebase does not create a merge commit.
- If conflicts occur during rebase:
  - Resolve the conflicts.
  - Run:
    ```bash
    git add .
    git rebase --continue
    ```
- If no conflicts occur, the rebase completes automatically.
- After a successful rebase, a force push (`--force-with-lease`) is required because commit history changes.

## Difference Between Merge and Rebase

### Merge

```
A---B---C (master)
     \     \
      D---E-M (feature)
```

- Creates a merge commit.
- Preserves complete history.

### Rebase

```
A---B---C---D'---E'
```

- No merge commit.
- Clean, linear history.
- Easier to read project history.

## Interview Questions

### What is Git Rebase?

Git Rebase moves the feature branch commits on top of the latest master branch to maintain a clean and linear Git history without creating a merge commit.

### Why use Rebase?

- Clean commit history
- No unnecessary merge commits
- Easier to review project history

### Difference between Merge and Rebase?

| Git Merge | Git Rebase |
|------------|------------|
| Creates a merge commit | No merge commit |
| Preserves branch history | Rewrites commit history |
| Non-linear history | Linear history |
| Safe for shared branches | Best before sharing changes |

## Result

Successfully rebased the feature branch with the master branch and pushed the updated branch to the remote repository.

✅ Challenge Completed Successfully
