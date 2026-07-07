# Day 30 - Git Hard Reset

## Objective
Reset the Git repository history so that only the required commits remain.

## What I Did
- Connected to the Storage Server.
- Navigated to the repository.
- Checked the commit history using `git log --oneline`.
- Identified the commit with the message `add data.txt file`.
- Reset the branch to that commit using a hard reset.
- Verified that only two commits remained.
- Force pushed the rewritten history to the remote repository.
- Confirmed the working tree was clean.

## Commands Used

```bash
cd /usr/src/kodekloudrepos/cluster
git log --oneline
git reset --hard 2d6c7e8
git log --oneline
git push origin master --force
git status
```

## Final Commit History

```text
2d6c7e8 add data.txt file
63fa33e initial commit
```

## Key Learnings

- `git reset --hard <commit>` resets the current branch, HEAD, and working directory to a specific commit.
- All commits after the target commit are removed from the local branch history.
- `git push --force` updates the remote repository with the rewritten history.
- Always use force push carefully because it rewrites shared Git history.
