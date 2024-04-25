# Git Commands

- [Git Commands](#git-commands)
  - [For general use:](#for-general-use)
  - [For examining differences:](#for-examining-differences)
  - [For checking out:](#for-checking-out)
  - [For branching:](#for-branching)
  - [For highlighting:](#for-highlighting)
  - [For deleting modifications:](#for-deleting-modifications)
  - [For new GitHub repo:](#for-new-github-repo)


## For general use:
```
git --version
git init
ls -a
git config --global user.email "andres.alamo@pucp.edu.pe"
git config --global user.name "Andy-Leo10"
git clone <REPO_URL>
git pull
git status
git add .
git commit -m "<MESSAGE>"
git commit -m "<MESSAGE>" --amend
git push
git log --oneline
```

## For examining differences:
```
git diff <COMMIT_HASH_1> <COMMIT_HASH_2>
git diff --staged
```

## For checking out:
```
git checkout <COMMIT_HASH>
git checkout main
git checkout HEAD~1
```

## For branching:
```
git branch <BRANCH_NAME>
git switch <BRANCH_NAME>
git branch <BRANCH_NAME> -d
git branch <BRANCH_NAME> -m
git merge <BRANCH_NAME>
```

## For highlighting:
```
git tag <TAG_NAME>
```

## For deleting modifications:
```
git reset --hard
git reset --hard <COMMIT_HASH>
```

## For new GitHub repo:
```
git remote add origin <REPO_URL>
git branch -M main
git push -u origin main
```