---
title: "git推送冲突🪢问题"
description: "git config pull.rebase true/false"
date: 2023-02-07
author: Tyler
tags: ["tips", "tech"]
categories:  ["Tech", "Tips"]
---
### 起因
今天在推送至github的时候出现了冲突，原因是因为昨天在github用在线编辑器修改了文件，
今天没有拉取就提交了，所以出现了冲突：
```

2023-02-07 17:56:00.671 [info] > git pull --tags origin main [4203ms]
2023-02-07 17:56:00.672 [info] From github.com:changzhenlin/hugo-repository
 * branch            main       -> FETCH_HEAD
hint: You have divergent branches and need to specify how to reconcile them.
hint: You can do so by running one of the following commands sometime before
hint: your next pull:
hint: 
hint:   git config pull.rebase false  # merge
hint:   git config pull.rebase true   # rebase
hint:   git config pull.ff only       # fast-forward only
```
### 日志给了三种解决办法

#### 合并： git config pull.rebase false
合并是把本地分支的提交历史与远程分支的提交历史合并到一起的方式。在合并的过程中，Git 会创建一个合并提交，其中包含了本地分支和远程分支的所有提交。

#### 变基： git config pull.rebase true
变基是把本地分支的提交历史“基于”远程分支的提交历史重新构建一遍的方式。在变基的过程中，Git 会把本地分支的提交一个一个地移动到远程分支的最新提交上面，并且在移动过程中适当地解决冲突。

#### 快进： git config pull.ff only
快进是把本地分支直接移动到远程分支的最新提交的方式。在快进的过程中，Git 不会创建任何合并提交或变基提交，而是直接把本地分支的HEAD指向远程分支的最新提交。

请注意，快进只有在远程分支是本地分支的祖先分支时才能使用，否则会报错。因此，使用快进需要谨慎，并且应该充分了解你的项目的代码历史。