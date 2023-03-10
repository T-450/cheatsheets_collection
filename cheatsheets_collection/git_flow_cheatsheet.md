git-flow-cheatsheet
===================

A cheatsheet on the usage of git flow, visit [Git Flow Cheat Sheet](https://danielkummer.github.io/git-flow-cheatsheet/#hotfixes)

GIT FLOW
========

Git extensions to provide high-level repository operations for Vincent Driessen's branching model. [Read more](http://nvie.com/posts/a-successful-git-branching-model/)

INIT:
Initializes a Git Flow repository in the current directory.

Please mercy to yourself and don’t set values in init.
Use the default values.

```shell
git flow init
```

#### TRACK DEVELOP REMOTELY ON GITHUB

```shell
git push origin develop
```

**Creating Branches:**

Use to develop new features starting from the develop branch. Merge back into
develop branch waiting for a reasonable amount of features to be there before
declaring it a release.

```shell
git flow feature
git flow feature start <name>
git flow feature finish <name>
```

```shell
# Usage: git flow feature [list] [-v]
       git flow feature start [-F] <name> [<base>]
       git flow feature finish [-rFk] <name|nameprefix>
       git flow feature publish <name>
       git flow feature track <name>
       git flow feature diff [<name|nameprefix>]
       git flow feature rebase [-i] [<name|nameprefix>]
       git flow feature checkout [<name|nameprefix>]
       git flow feature pull <remote> [<name>]
```

**RELEASES:**

Use to group together latest development (features) add a few finishing touches
if necessary and send to production. All last changes will merge back to master
and develop so new features will start from current release.

```shell
git flow release
git flow release start <release> [<base>]
git flow release finish <release>
```

```shell
# Usage: git flow release [list] [-v]
       git flow release start [-F] <version>
       git flow release finish [-Fsumpk] <version>
       git flow release publish <name>
       git flow release track <name>
```

**HOTFIXES:**

Similar to releases but the hotfix branch starts off master to avoid unvoluntary
send to production of unwanted features that my be present in branches. The
quick fix must be used when an important bug arises in production which must be
fixed and can't wait for other features to be ready. It merges back to master
and develop.

```shell
git flow hotfix
git flow hotfix start <release> [<base>]
git flow hotfix finish <release>
```

```shell
# Usage: 
git flow hotfix [list] [-v]
git flow hotfix start [-F] <version> [<base>]
git flow hotfix finish [-Fsumpk] <version>
```
