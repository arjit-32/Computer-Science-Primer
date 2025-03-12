---
title: Reflog
author: Arjit Sharma
courses: ["git"]
categories: ["Development-Plus"]
featured: false
draft: false
---

Reflog stands for Reference Log, it is like a hidden  "undo history”. Lets say you remove the last commit or mess with history, git still keeps track of them for some time.

```bash
git checkout HEAD^ // refers to parent commit of current HEAD, move back 1 commit
git branch -f master // Force creation of new branch master, reset master branch to previous commit 
git checkout master // Switch working directly to newly created master branch
git log
```

![Untitled](https://res.cloudinary.com/dwa6rcttw/image/upload/v1741781683/Untitled_11_iqzpnv.png)

Reflog records all movements of branches in the repository. It is a history of changes made to the HEAD. It contains reference to the state of repo at various points, even if those points are no longer reachable within the repo.

```bash
git reflog
git reset --hard 9223a7a # Check the commit you want to restore
```