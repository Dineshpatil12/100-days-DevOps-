# Day 27 - Git Revert Some Changes

## Objective
Revert the latest commit in a Git repository using `git revert`.

## Commands Used

```bash
git log --oneline
git revert HEAD --no-edit
git commit --amend -m "revert beta"
git status
