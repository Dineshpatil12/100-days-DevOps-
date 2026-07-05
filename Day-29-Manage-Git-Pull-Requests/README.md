# Day 29: Manage Git Pull Requests (PR)

## Objective
Learn how to manage Pull Requests (PRs) using Gitea by following a real-world Git collaboration workflow.

## What I Practiced

- Verified Git branches and commit history.
- Created a Pull Request (PR) from a feature branch to the `master` branch.
- Added a reviewer to the Pull Request.
- Reviewed and approved the Pull Request as another user.
- Updated an out-of-date feature branch with the latest changes from `master`.
- Successfully merged the Pull Request into the `master` branch.
- Verified the merge using Git commands.

## Git Commands Used

```bash
git branch -a
git log
git checkout story/fox-and-grapes
git merge origin/master
git push origin story/fox-and-grapes
git checkout master
git pull origin master
git log --oneline --graph --decorate
```

## Pull Request Workflow

```text
Create Feature Branch
        │
        ▼
Make Changes
        │
        ▼
Commit Changes
        │
        ▼
Push Branch to Remote
        │
        ▼
Create Pull Request
        │
        ▼
Assign Reviewer
        │
        ▼
Review & Approve
        │
        ▼
Merge Pull Request
        │
        ▼
Pull Latest Changes
        │
        ▼
Verify Merge History
```

## Key Learning

- A Pull Request allows code to be reviewed before merging.
- Reviewers help maintain code quality and collaboration.
- Protected branches prevent direct changes to the main branch.
- Keeping a feature branch up to date with the target branch helps avoid merge issues.
- Always verify the merge using `git log` after completion.

## Outcome

Successfully completed the **Day 29: Manage Git Pull Requests** lab by creating, reviewing, approving, and merging a Pull Request using Gitea.
