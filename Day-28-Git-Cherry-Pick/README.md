# Day 28: Git Cherry Pick

## Objective

Learn how to use Git Cherry-Pick to apply a specific commit from one branch to another without merging the entire branch.

## Scenario

The development team had two branches:

* master
* feature

The feature branch contained multiple commits, but only one commit with the message **"Update info.txt"** needed to be moved to the master branch.

The task was to cherry-pick the required commit and push the changes to the remote repository.

## Repository Structure

```text
master
│
├── Add welcome.txt
│
feature
├── Update info.txt
└── Update welcome.txt
```

## Commands Used

### Navigate to Repository

```bash
cd /usr/src/kodekloudrepos/apps
```

### View Available Branches

```bash
git branch -a
```

### Switch to Feature Branch

```bash
git checkout feature
```

### Find the Required Commit

```bash
git log --oneline --grep="Update info.txt"
```

Output:

```bash
7f3a034 Update info.txt
```

### Switch to Master Branch

```bash
git checkout master
```

### Cherry-Pick the Commit

```bash
git cherry-pick 7f3a034
```

### Push Changes

```bash
git push origin master
```

## Verification

Check whether the commit changes are available on master:

```bash
git cherry -v master feature
```

Output:

```bash
- 7f3a034 Update info.txt
+ ff76b0e Update welcome.txt
```

Explanation:

* (-) indicates the commit changes already exist in master.
* (+) indicates the commit is not yet present in master.

## Key Learning

### Git Cherry-Pick

Git Cherry-Pick allows you to apply a specific commit from one branch to another without merging the entire branch.

Syntax:

```bash
git cherry-pick <commit-id>
```

### Merge vs Cherry-Pick

| Merge                                | Cherry-Pick                |
| ------------------------------------ | -------------------------- |
| Merges all commits                   | Copies selected commit(s)  |
| Preserves branch history             | Creates a new commit       |
| Used for complete branch integration | Used for selective changes |

## Outcome

Successfully cherry-picked the **Update info.txt** commit from the feature branch to the master branch and pushed the changes to the remote repository.

## Skills Practiced

* Git Branch Management
* Git Cherry-Pick
* Commit Identification
* Repository Verification
* Git Push Operations
* DevOps Version Control Workflow

---

**Day 28 of #100DaysOfDevOps**

