# Day 33: Resolve Git Merge Conflicts

## Task

Sarah and Max were working on the same `story-blog` Git repository.

Max had local changes and tried to push them to the remote repository, but the push was rejected because the remote branch already had new commits.

The goal was to:

* Pull the latest remote changes
* Resolve the merge conflict in `story-index.txt`
* Keep titles for all 4 stories
* Correct the typo `Mooose` to `Mouse`
* Commit the resolved changes
* Push the final changes successfully to the remote repository

---

## Repository Details

Repository path:

```bash
/home/max/story-blog
```

Branch:

```bash
master
```

Remote repository:

```bash
http://gitea:3000/sarah/story-blog.git
```

---

## Step 1: Connect to the Storage Server

SSH into the storage server using user `max`:

```bash
ssh max@ststor01
```

Then navigate to the repository:

```bash
cd /home/max/story-blog
```

Verify the current branch and repository status:

```bash
pwd
git status
git branch
```

The local branch was ahead of `origin/master` by one commit.

---

## Step 2: Try to Push the Local Changes

Command:

```bash
git push origin master
```

The push was rejected:

```text
! [rejected] master -> master (fetch first)
error: failed to push some refs to 'http://gitea:3000/sarah/story-blog.git'
```

Git also showed:

```text
Updates were rejected because the remote contains work that you do not
have locally.
```

### Reason

The remote `master` branch had new commits that were not available in Max's local repository.

Because of this, Git did not allow the local branch to overwrite the remote history.

---

## Step 3: Pull the Remote Changes

Command:

```bash
git pull origin master
```

Git downloaded the remote changes but found a conflict:

```text
Auto-merging story-index.txt
CONFLICT (add/add): Merge conflict in story-index.txt
Automatic merge failed; fix conflicts and then commit the result.
```

---

## Step 4: Check the Merge Conflict

Commands:

```bash
git status
cat story-index.txt
```

The file contained Git conflict markers:

```text
<<<<<<< HEAD
1. The Lion and the Mooose
2. The Frogs and the Ox
3. The Fox and the Grapes
4. The Donkey and the Dog
=======
1. The Lion and the Mouse
2. The Frogs and the Ox
3. The Fox and the Grapes
>>>>>>> c8e588bd743268ba4b4a17d5eb4e1c53c24990c1
```

### Conflict Explanation

The section between:

```text
<<<<<<< HEAD
```

and:

```text
=======
```

represented the local changes.

The section between:

```text
=======
```

and:

```text
>>>>>>> commit-id
```

represented the remote changes.

Git could not decide automatically which version should be kept.

---

## Step 5: Resolve the Merge Conflict

The correct final content of `story-index.txt` was:

```text
1. The Lion and the Mouse
2. The Frogs and the Ox
3. The Fox and the Grapes
4. The Donkey and the Dog
```

The typo was also corrected:

```text
The Lion and the Mooose
```

to:

```text
The Lion and the Mouse
```

All Git conflict markers were removed.

The file was updated using:

```bash
cat > story-index.txt <<'EOF'
1. The Lion and the Mouse
2. The Frogs and the Ox
3. The Fox and the Grapes
4. The Donkey and the Dog
EOF
```

---

## Step 6: Verify the Resolved File

Commands:

```bash
cat story-index.txt
git status
```

Final file content:

```text
1. The Lion and the Mouse
2. The Frogs and the Ox
3. The Fox and the Grapes
4. The Donkey and the Dog
```

The file still appeared as unmerged until it was staged.

---

## Step 7: Stage the Resolved File

Command:

```bash
git add story-index.txt
```

By running `git add`, Git was informed that the merge conflict had been resolved.

---

## Step 8: Commit the Merge Resolution

Command:

```bash
git commit -m "Resolve merge conflict in story index"
```

Output:

```text
[master 1301fd9] Resolve merge conflict in story index
```

The merge resolution was successfully committed.

---

## Step 9: Push the Final Changes

Command:

```bash
git push origin master
```

The push completed successfully.

This synchronized the local `master` branch with the remote `origin/master` branch.

---

## Step 10: Final Verification

Commands:

```bash
git status
git log --oneline --graph --all --decorate -6
cat story-index.txt
```

Final Git status:

```text
nothing to commit, working tree clean
```

Git log:

```text
*   1301fd9 (HEAD -> master, origin/master, origin/HEAD) Resolve merge conflict in story index
|\
| * c8e588b Added Index
* | e90ea7c Added the fox and grapes story
|/
*   3359b07 Merge branch 'story/frogs-and-ox'
|\
| * 87dd691 Completed frogs-and-ox story
| * f02a07b Add incomplete frogs-and-ox story
```

Final `story-index.txt`:

```text
1. The Lion and the Mouse
2. The Frogs and the Ox
3. The Fox and the Grapes
4. The Donkey and the Dog
```

---

## Important Git Commands Used

```bash
ssh max@ststor01
cd /home/max/story-blog

git status
git branch

git push origin master

git pull origin master

git status
cat story-index.txt

git add story-index.txt

git commit -m "Resolve merge conflict in story index"

git push origin master

git status
git log --oneline --graph --all --decorate -6
cat story-index.txt
```

---

## Git Merge Conflict Workflow

A common Git conflict-resolution workflow is:

```bash
git pull
git status
```

Identify the conflicted files.

Manually resolve the conflict and remove:

```text
<<<<<<<
=======
>>>>>>>
```

Then run:

```bash
git add <file>
git commit
git push
```

---

## Why `git push --force` Was Not Used

Using:

```bash
git push --force
```

could overwrite remote commits and potentially remove Sarah's changes.

The correct approach was to:

```text
Pull → Merge → Resolve Conflict → Commit → Push
```

This preserved both Sarah's and Max's work.

---

## Key Learning

A Git merge conflict occurs when Git cannot automatically combine changes from different branches or commits.

In this task:

* Max had one local commit.
* Sarah had one remote commit.
* Both versions affected `story-index.txt`.
* Git could not merge them automatically.
* The conflict was resolved manually.
* All four story titles were preserved.
* The typo was corrected.
* The final merge was committed and pushed successfully.

---

## Interview Explanation

> My Git push was rejected because the remote branch had new changes that were not available locally. I pulled the latest remote changes, which created a merge conflict in `story-index.txt`. I checked both local and remote changes, manually resolved the conflict, preserved all four story titles, corrected the typo from `Mooose` to `Mouse`, staged the file, committed the merge resolution, and pushed the final changes successfully.

---

## Result

Challenge completed successfully.

Reference ID:

```text
68078704399a2462b6cc6684
```

## Status

✅ Day 33 Completed Successfully
✅ Merge Conflict Resolved
✅ All 4 Story Titles Preserved
✅ Typo Corrected
✅ Changes Committed
✅ Changes Pushed to Remote Repository

