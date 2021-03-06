## Git Manual

> คู่มือการใช้งาน Git

## Table of Contents

- [Install](#install)
- [Generating a new SSH key](#generating-a-new-ssh-key)
- [Adding SSH key to the ssh-agent](#adding-ssh)
- [Show SSH and GPG keys](#ssh-and-gpg-keys)
- [Setting Config](#setting-config)
- [Install Git Flow](#install-git-flow)
- [Git Remote](#git-remote)
- [Git Changed Repo](#git-changed-repo)

## Install

```
sudo apt install -y git
```

## Generating a new SSH key

```
ssh-keygen -t rsa -b 4096 -C "youremail@example.com"
```

## Adding SSH

```
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_rsa
```

## SSH and GPG keys

```
cat .ssh/id_rsa.pub
```

## Setting Config

```
git config --global user.email "youremail@example.com"
git config --global user.name "Your Name"
```

## Install Git Flow

```
sudo apt install -y git-flow
```

## Git Clone

```
git clone your-repo
```

## Init Git Flow

```
git flow init
```

## Git Add

```
git add .
```

## Git Commit

```
git commit -m "commit description"
```

## Git Push

push ครั้งแรก ของ branch จะต้อง set upstream ที่จะ push ไป

```
git push --set-upstream origin develop

or

git push -u origin develop
```

หลังจากนั้นจะใช้คำสั่ง push ตามปกติ

```
git push || git push origin-name branch-name
```

## Git Pull

```
git pull
```

## Git Merge

```
git merge branch-name
```

## Git Branch

สร้าง branch ใหม่

```
git branch branch-name

or

git branch branch-name --track local-branch-name
```

ลบ branch local

```
git branch -D branch-name
```

ลบ branch origin

```
git push origin --delete branch-name
```

ดูว่ามี branch อะไรบ้าง

```
git branch || git branch -a
```

กรณีต้องการให้ origin branch ใน local เท่ากับ origin upstream

```
git fetch --prune
```

## Git Flow Feature Start

```
git flow feature start feature-name
```

## Git Flow Feature Finish

```
git flow feature finish feature-name
```

## Git Flow Release Start

```
git flow release start release-name
```

## Git Flow Release Finish

```
git flow release finish release-name
```

## Git Checkout

```
git checkout branch-name
```

## Git Status

```
git status
```

## Git Delete Local Tag

ลบแบบ tag เดียว

```
git tag -d tag-name
```

ลบแบบหลาย tag

```
git tag -l | xargs git tag -d
```

## Git Delete Origin Tag

ลบแบบ tag เดียว

```
git push --delete origin tag-name
```

ลบแบบหลาย tag

```
git tag -l | xargs -n 1 git push --delete origin
```

## Git Fetch

```
git fetch

or

git fetch remote-name

or

git fetch --prune || git fetch -p
```

## Git Remote

```
git remote add origin repo-name
git remote rm origin-name
git remote -v

# หลังจากสร้าง upstream ให้ update remote
git remote update

# กรณี add upstream ใหม่แล้ว fetch upstream ไม่เจอ branch ให้ push -u upstream {branch}
git push -u gitlab develop
```

## Git Log

```
git log
```

## Git Tree

```
git config --global alias.tree "log --oneline --decorate --all --graph"
git tree
```

## Git Diff

```
git diff || git diff file-name
```

## Git Revert

```
git revert <commit>
```

## Git Reset

```
git reset --hard <commit>
```

## Git Cherry Pick

```
git cherry-pick <commit>
```

## Git Changed Repo

```
git remote set-url origin <new repo>
```
