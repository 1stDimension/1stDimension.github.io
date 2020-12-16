---
layout: post
author: 1stDimension
title: Private posts on Github
excerpt: How to have private and public blog using Github Pages, git with multiple
  environments.
date: 2020-10-01 00:03 +0200
---
## How Github Pages works

Github Pages is a feature of Github that allows serving static files. This very site is
accessible thanks to this service. There are limitations. The free plan only includes public
repo. Paid plans include private ones, the site will still be accessible to the public. This
is excellent but public repos have their problems. First of all, everything is public. This
includes work in progress posts, not everything of which might be released. It is very hard
to create a workflow of releasing only completed posts to the public. You could use branches
of git. Have a branch for each post and when ready merge them into master. Yet posts will be
accessible on the branch's page before going public. Good but we can do better using one of
git's features, remotes.

## Git a distributed version control system (VCS)

Git is distributed by nature. Everyone using the system is copying the entire history of changes.
One client can also operate with many servers, called remotes in git. You can look up
remotes where your code will be uploaded using this command

```sh
$ git remote -v # -v is just for verbose output
origin  git@github.com:1stDimension/1stDimension.git (fetch)
origin  git@github.com:1stDimension/1stDimension.git (push)
```
The left column contains names of remotes. The right column contains the URL of where to send changes (*push*) and from
where copy changes (*fetch*). Origin is the name of the default remote.

In the example above both URLs are the same but they don't have to. This results in sth called
"Triangular workflow". Michael Haggerty described it on "The GitHub Blog" [here](https://github.blog/2015-07-29-git-2-5-including-multiple-worktrees-and-triangular-workflows/#improved-support-for-triangular-workflows)

## Multiple remotes as multiple environments for Github 

Remotes are nice and all but how do they solve the problem with all public repos. You can simply
create 2 repos on Github one private, let's call it *working*, one public, let's call it *publish*.
Use working as main repository you push your changes to. For example, when you finish working on your blog post, you can marge “post branch” into a branch from which GitHub pages are served. Then push
changes to *publish* repo. Now WIP posts are hidden and pages can be served with a free plan. But how
do we do it? With ```git remote commands```

```sh
# Assuming you are on a branch you want to publish
# Adding remote "publish"
$ git remote add publish {% raw %}{{ remote url }}{% endraw %}
# Update existing remotes url
$ git remote set-url  {% raw %}}{{ remote name }} {{ remote url }}{% endraw %}
# List remotes new one should show up
$ git remote -v
# push current branch to remote "publish"
$ git push publish 
```

And now changes are pushed to repo where GitHub will generate static files and publish GitHub Pages

## Bibliography

1. [About GitHub Pages](https://docs.github.com/en/github/working-with-github-pages/about-github-pages)
1. [Git 2.5, including multiple worktrees and triangular workflows](https://github.blog/2015-07-29-git-2-5-including-multiple-worktrees-and-triangular-workflows/)
1. [git-remote](https://git-scm.com/docs/git-remote)
1. [Git Basics - Working with Remotes](https://git-scm.com/book/en/v2/Git-Basics-Working-with-Remotes)
1. [Integration-Manager Workflow](https://git-scm.com/book/en/v2/Distributed-Git-Distributed-Workflows)