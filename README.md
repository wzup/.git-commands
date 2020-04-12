# Useful .git commands

### git cat-file -p 875ab93

To see **commit's parents**, **author** and **commiter** ([source](https://blog.developer.atlassian.com/pull-request-merge-strategies-the-great-debate/))

```bash
$ git cat-file -p 127196

tree e8a13dd4283eb2635c42079fa77c3480bd153c97

parent 8bd43d673fcf1239e36ec33cbc8d22806461e757

parent 38f8f7b1afc81f74ee2c8d93c359b19636b9d6b1

author Nicola Paolucci <xxxxx@atlassian.com> 1412938811 +0200

committer Nicola Paolucci <xxxxx@atlassian.com> 1412938811 +0200

Merge branch 'test-branch'
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

## Other commands
git log --first-parent
