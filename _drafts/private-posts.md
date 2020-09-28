---
layout: post
author: 1stDimension
title: Private posts on Github
excerpt: How to have private and public blog using Github Pages, git with multiple remotes.
---

## How Github Pages works
Github Pages is a feature of Github that allows serving static files. This very site is
accessible thanks to this service. There are limitations. The free plan only includes public
repo. Paid plans include private ones, the site will still be accessible to the public. This
is excellent but public repos have their problems. First of all, everything is public. This
includes work in progress posts, not everyone  of which might be released. It is very hard
to create a workflow of releasing only completed posts to the public. You could use branches
of git. Have a branch for each post and when ready merge them into master. Yet posts will be
accessible on the branch's page before going public. Good but we can do better.

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