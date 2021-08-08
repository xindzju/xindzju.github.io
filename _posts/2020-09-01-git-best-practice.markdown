---
layout: post
title:  "Git best practice"
date:   2020-09-01 16:17::00
categories: blog
---

## Standarlize git commit
#### &lt;type&gt;(&lt;scope&gt;): &lt;subject&gt;

## Description
#### &lt;type&gt;(must have)
* feat: new feature
* fix: bug fix
* perf: perfomance related
* refactor: code refactor
* test: add testing
* docs: documentation
* chore: build related
* revert: revert to specific commit
* merge: code merge
* style: format related, doesn't change code logic

#### &lt;scope&gt;(optional)
The sphere of influence of your commit, like UI, Backend or a specific component/module of your project.

#### &lt;subject&gt;(must have)
A concise and informative description of your commit

## The difference between git revert and git reset
* git reset --soft commit/tag
delete commits before this target commit but keep changes
* git reset --hard commit/tag 
delete commits before this target commit and also including corresponding changes

* git revert
will add one more commit for this operation## Git submodule

