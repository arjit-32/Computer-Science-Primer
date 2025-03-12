---
title: Git Submodules
author: Arjit Sharma
courses: ["git"]
categories: ["Development-Plus"]
featured: false
draft: false
---


## What Are Git Submodules?

A **Git submodule** is a repository inside another repository. It allows you to **include external projects** in your repo while keeping them separate.
It becomes quite useful as it keep’s external repo’s history seperate from your main project and can freeze a dependency at a specific version.

```bash
git submodule add <url>
```

This will create a `.gitmodules` file that tracks submodules in your project.

## Cloning Repository with Submodules

```bash
git clone --recurse-submodules <repo-url>
```