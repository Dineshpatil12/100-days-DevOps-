# Day 26 - Git Manage Remotes

## Objective

Manage Git remotes, commit changes to a repository, and push updates to a newly configured remote repository.

## Task Details

The repository was available at:

```bash
/usr/src/kodekloudrepos/ecommerce
```

### Requirements

1. Add a new remote named `dev_ecommerce`.
2. Point the remote to:

   ```bash
   /opt/xfusioncorp_ecommerce.git
   ```
3. Copy the file:

   ```bash
   /tmp/index.html
   ```

   into the repository.
4. Add and commit the file to the `master` branch.
5. Push the `master` branch to the new remote.

## Commands Used

```bash
cd /usr/src/kodekloudrepos/ecommerce

git remote add dev_ecommerce /opt/xfusioncorp_ecommerce.git

cp /tmp/index.html .

git add index.html

git commit -m "added index.html"

git push dev_ecommerce master
```

## Verification

Check configured remotes:

```bash
git remote -v
```

Check latest commit:

```bash
git log --oneline -1
```

## Output

```bash
dev_ecommerce   /opt/xfusioncorp_ecommerce.git (fetch)
dev_ecommerce   /opt/xfusioncorp_ecommerce.git (push)
```

```bash
fd26f1c added index.html
```

## Key Git Concepts

### Add Remote Repository

```bash
git remote add <remote_name> <repository_path>
```

### View Remotes

```bash
git remote -v
```

### Commit Changes

```bash
git add .
git commit -m "commit message"
```

### Push to Specific Remote

```bash
git push <remote_name> <branch_name>
```

## Learning Outcome

* Learned how to configure multiple Git remotes.
* Practiced committing changes to a repository.
* Understood how to push code to a specific remote.
* Verified remote configurations and commit history.

## Status

✅ Challenge Completed Successfully

**Reference ID:** 68077d2b399a2462b6cc667c

