---
layout: post
author: 1stDimension
title: Private posts on Github
excerpt: How to have private and public blog using Github Pages, git with multiple remotes.
---

## How Github Pages works
Github Pages is a feature of Github that allows serving static files. This very site is accessible
thanks to this service.There are limitations. Free plan only includes public repo, paid plans
include private ones, site will still be accessible to the public. This is excellent but public
repos have their problems. First of all everything is public, that includes work in progres posts,
not all from which might be released. It is very hard to create workflow of releasing only completed
posts to the public. You could utilize branches of git. Have branch for each post and when ready
just merge them into master. However posts will be publicly accessible on branch's page before going
public. Good but we can do better.

## Git a distributed version control system

Here are remotes 
```sh
$ git remote -v
origin  git@github.com:1stDimension/1stDimension.git (fetch)
origin  git@github.com:1stDimension/1stDimension.git (push)
```

## Multiple remotes as multiple environments for Github 

## Bibliography

1. [About GitHub Pages](https://docs.github.com/en/github/working-with-github-pages/about-github-pages)
1. [git-remote](https://git-scm.com/docs/git-remote)
1. [Git Basics - Working with Remotes](https://git-scm.com/book/en/v2/Git-Basics-Working-with-Remotes)
1. [Integration-Manager Workflow](https://git-scm.com/book/en/v2/Distributed-Git-Distributed-Workflows)