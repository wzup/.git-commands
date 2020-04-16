# Useful .git commands

### git cat-file 875ab93

To see **commit's parents**, **author** and **commiter** ([source](https://blog.developer.atlassian.com/pull-request-merge-strategies-the-great-debate/))

`-p` - pretty-print object's content
`-t` - show object type
`-s` - show object size

```bash
$ git cat-file 127196 -p
tree e8a13dd4283eb2635c42079fa77c3480bd153c97
parent 8bd43d673fcf1239e36ec33cbc8d22806461e757
parent 38f8f7b1afc81f74ee2c8d93c359b19636b9d6b1
author Nicola Paolucci <xxxxx@atlassian.com> 1412938811 +0200
committer Nicola Paolucci <xxxxx@atlassian.com> 1412938811 +0200
Merge branch 'test-branch'

$ git cat-file 127196 -t
blob
```

### git log --pretty=format:"%h:  %d" -1

To format `git log` ([source](https://stackoverflow.com/a/54935492/1114926))

```bash
$ git log --pretty=format:"%h:  %d" -3
005c52e:   (HEAD -> add-scss, origin/add-scss)
820cb1c:   (origin/master, master)
875ab93:
```

### git log --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit

A better `git log` ([source](https://coderwall.com/p/euwpig/a-better-git-log))

```bash
$ git log --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit

* 71ab5f13d - (HEAD -> master, origin/master, origin/HEAD) Merged PR 5266: ERD-2578 [Testing] Tests for Recovery component fail. Fix it (7 weeks ago) <Sergey Reznikov>
* 847f15876 - Merged PR 5264: ERD-2574 [Application] Incorrect data-test-id (8 weeks ago) <Sergey Reznikov>
* 08304e689 - Merged PR 5219: ERD-1478 Design updates to landing page (8 weeks ago) <Sergey Reznikov>
* 9b1992e34 - Merged PR 5161: ERD-2389 Refactor Auth Module (8 weeks ago) <Sergey Reznikov>
* dcebeef91 - Merged PR 5257: fix: (scientific reviewer) change button style (8 weeks ago) <Igor Boiko>
* 2dd3bf8de - Merged PR 5259: fix: (lint) fix lint error (8 weeks ago) <Igor Boiko>
* 81c7e7eb2 - Merged PR 5258: fix: (test) fix tests (8 weeks ago) <Igor Boiko>
```

### cat .git/HEAD

To see HEAD's position ([source](https://stackoverflow.com/a/54935492/1114926))

```bash
$ cat .git/HEAD
ref: refs/heads/add-scss
```

### git hash-object file.js

To get SHA1 key of the value.
Value should be a file, not a string ([source](https://app.pluralsight.com/course-player?clipId=5326515f-7c84-4c87-afa6-e8a3b91aa93b))

`-w` write content to git repository

```bash
// A value is a file
$ git hash-object file.js
9a00219dfec4b54f4791437575505abdd50e56c5

// A value is a string
$ echo "Apple Pie" | git hash-object --stdin
23991897e13e47ed0adb91a0082c31c82fe0cbe5
```

### git count-objects

To calculate objects in objects DB `.git/objects` ([source](https://app.pluralsight.com/course-player?clipId=ecabaccf-18fb-4a5c-b2d8-d35f730c1721))

```bash
$ git count-objects
20 objects, 80 kilobytes
```

### git tag -a mytag -m "I love cheesecake"

To add annotated tag ([source](https://app.pluralsight.com/course-player?clipId=65c52ba1-988c-439c-81df-b1511b2d0530))

```bash
$ git tag -a mytag -m "I love cheesecake"
$ git tag
mytag
```

### git show-ref master | origin/master | HEAD | origin/HEAD

To list all of the branches that have `master` in their name

```bash
$  git show-ref master
704182f5e2925fbdc03f9874d35ce696c21e9a3d refs/heads/master
704182f5e2925fbdc03f9874d35ce696c21e9a3d refs/remotes/origin/master
```

### git merge-base feature1 master

To get SHA-1 of the commit `feature1` branched off of master. Good for `rebase` and `squash`

```bash
$ git checkout ERD-2356
$ git merge-base ERD-2356 master
a8469914bcb6e2dc258e850bedf9660f0405bf00

$ git rebase -i a846991
$ 
```

## Other commands
git log --first-parent
