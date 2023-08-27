# ![](https://overthewire.org/img/domokitten.png)

# Bandit_Level29

## Source:
- [Bandit_Level29] - The topic of Bandit, Level29.
###
### I. Connect:
```sh
ssh -p 2220 bandit28@bandit.labs.overthewire.org
Password: AVanL161y9rsbcJIsFHuw35rjaOM19nR
```
###
### II. My solution:
- Simillar with previous level, we create a temporily directory: `mkdir /tmp/tmp_28` then `cd /tmp/tmp_28`.
> Answer: `git clone ssh://bandit28-git@localhost:2220/home/bandit28-git/repo`.
- After that, a new directory appear in git_tmp directory: `repo` then `cd repo`
- Check directory: `ls`. -> There are a file named `README`.
- Check file format of `README`: `file README` -> ASCII text.
- Read it: `cat README`
```sh
# Bandit Notes
Some notes for level29 of bandit.

## credentials

- username: bandit29
- password: xxxxxxxxxx
```

- Password for next level is hiddened, so we find an alternative way.
- `cd ./.git` then,
- `git log` command can help us in showing all of commits.
```sh
commit 899ba88df296331cc01f30d022c006775d467f28 (HEAD -> master, origin/master, origin/HEAD)
Author: Morla Porla <morla@overthewire.org>
Date:   Sun Apr 23 18:04:39 2023 +0000

    fix info leak

commit abcff758fa6343a0d002a1c0add1ad8c71b88534
Author: Morla Porla <morla@overthewire.org>
Date:   Sun Apr 23 18:04:39 2023 +0000

    add missing data

commit c0a8c3cf093fba65f4ee0e1fe2a530b799508c78
Author: Ben Dover <noone@overthewire.org>
Date:   Sun Apr 23 18:04:39 2023 +0000

    initial commit of README.md
```
- `git show <commit_name>` can help show various types of objects involed that commit.
- We check the first commit: `git show 899ba88df296331cc01f30d022c006775d467f28`
```sh
commit 899ba88df296331cc01f30d022c006775d467f28 (HEAD -> master, origin/master, origin/HEAD)
Author: Morla Porla <morla@overthewire.org>
Date:   Sun Apr 23 18:04:39 2023 +0000

    fix info leak

diff --git a/README.md b/README.md
index b302105..5c6457b 100644
--- a/README.md
+++ b/README.md
@@ -4,5 +4,5 @@ Some notes for level29 of bandit.
 ## credentials

 - username: bandit29
-- password: tQKvmcwNYcFS6vmPHIUSI3ShmsrQZK8S
+- password: xxxxxxxxxx
```

- Fortunately, there is bandit29's password.
###
### III. Result:
The password for next level: `tQKvmcwNYcFS6vmPHIUSI3ShmsrQZK8S`

[Bandit_Level29]: <https://overthewire.org/wargames/bandit/bandit29.html>
