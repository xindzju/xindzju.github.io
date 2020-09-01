---
layout: post
title:  "Git best practice"
date:   2020-09-01 16:17::00
categories: blog
---

origin: remote name
master: branch name

## the difference between git revert and git reset
* git reset --soft commit/tag
delete commits before this target commit but keep changes
* git reset --hard commit/tag 
delete commits before this target commit and also including corresponding changes

* git revert
will add one more commit for this operation

**To be continued, will keep updating**
