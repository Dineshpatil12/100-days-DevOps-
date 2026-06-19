# Git Merge Branches

## Objective
Create a new branch `nautilus`, add `index.html`, commit the changes, merge the branch into `master`, and push both branches to the remote repository.

## Steps Performed
1. Created branch `nautilus` from `master`.
2. Copied `index.html` into the repository.
3. Added and committed the file.
4. Pushed `nautilus` branch to origin.
5. Merged `nautilus` into `master`.
6. Pushed `master` branch to origin.

## Git Commands Used

```bash
git checkout -b nautilus
cp /tmp/index.html .
git add index.html
git commit -m "Added index.html file"
git push origin nautilus
git checkout master
git merge nautilus
git push origin master
