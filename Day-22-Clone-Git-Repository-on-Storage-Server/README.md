# Clone Git Repository on Storage Server

## Objective

Clone an existing Git repository from the storage server repository path to the specified destination directory using the `natasha` user.

## Task Details

- Source Repository: `/opt/apps.git`
- Destination Directory: `/usr/src/kodekloudrepos`
- User: `natasha`
- Server: `ststor01`

## Commands Used

```bash
ssh natasha@ststor01

cd /usr/src/kodekloudrepos

git clone /opt/apps.git
```

## Verification

List the cloned repository:

```bash
ls -l /usr/src/kodekloudrepos
```

Output:

```text
apps
```

Check repository status:

```bash
cd /usr/src/kodekloudrepos/apps
git status
```

Output:

```text
On branch master

No commits yet

nothing to commit
```

## Notes

- The source repository was empty, so Git displayed:

```text
warning: You appear to have cloned an empty repository.
```

- This is expected behavior and does not indicate a failure.
- No permissions or existing directories were modified.

## Learning Outcome

- Clone a local Git repository.
- Work with Git repositories using a non-root user.
- Verify cloned repositories using Git commands.
- Understand the difference between an empty repository and a failed clone operation.
