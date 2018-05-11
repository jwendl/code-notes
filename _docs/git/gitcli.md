---
title: Git Command Line
category: Git
order: 1
---
# Git Command Line

## Create a Patch using a Diff between HEAD and local

``` bash
git diff --patch --ignore-space-change --ignore-all-space
```

> This is good when we want to create a file that we can send to someone else to see the changes that we did to our local repository between our un committed changes and what is in the repository.
