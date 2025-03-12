---
title: Squashing commits with Rebase
author: Arjit Sharma
courses: ["git"]
categories: ["Development-Plus"]
featured: false
draft: false
---


When working on a feature, you often make multiple small commits. Instead of merging them all separately, you can **squash** them into a single meaningful commit using **interactive rebase**. This makes your Git history cleaner and easier to read.

In order to squash commits we will need reference to 

- Latest commit
- Oldest commit(can get using command `git rev-list --max-parents=0 HEAD`).

```bash
git rebase -i $(git rev-list --max-parents=0 HEAD) HEAD
```

On using this command, we will get an editable file of all the commits where we can specify the commits we want to -

- **pick** → Keep commit as it is.
- **squash (s)** → Merge commit with the previous one.
- **drop (d)** → Remove commit from history.

![Untitled](https://res.cloudinary.com/dwa6rcttw/image/upload/v1741781865/Untitled_12_yqrqgf.png)

After editing the file and saving it, Git will prompt you to rewrite the commit message for the squashed commits. Modify the message as needed, then continue:

```bash
git rebase --continue
```

Some points to note - 

- The **initial commit must be included** since every commit needs a base reference.
- After rebasing, you may end up in a **detached HEAD** state because Git moves commits but doesn't update the branch pointer. To fix this:
    
```bash
git branch -f master
git checkout master
```