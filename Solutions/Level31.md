# ![](https://overthewire.org/img/domokitten.png)

# Bandit_Level31

## Source:
- [Bandit_Level31] - The topic of Bandit, Level31.
###
### I. Connect:
```sh
ssh -p 2220 bandit30@bandit.labs.overthewire.org
Password: xbhV3HpNGlTIdnjUrdAlPzc2L6y9EOnS
```
###
### II. My solution:
- Similar to previous level, firstly create a temporarily directory: `mkdir /tmp/git_31` then `cd /tmp/git_31`
- In git_31 directory: `git clone ssh://bandit30-git@localhost:2220/home/bandit30-git/repo`
- Type `yes` and enter the bandit30's password.
- Check `git_31` directory: `ls` then `cd repo`
- In `repo` directory:
  - `ls` -> There is a markdown file `README.md` -> Read it: `cat README.md`:
    ```sh
    just an epmty file... muahaha
    ```
  - Check commit: `git log`:
    ```sh
    commit 59530d30d299ff2e3e9719c096ebf46a65cc1424 (HEAD -> master, origin/master, origin/HEAD)
    Author: Ben Dover <noone@overthewire.org>
    Date:   Sun Apr 23 18:04:42 2023 +0000

    initial commit of README.md
    ```
  - Show commit: `git show 59530d30d299ff2e3e9719c096ebf46a65cc1424`:
    ```sh
    commit 59530d30d299ff2e3e9719c096ebf46a65cc1424 (HEAD -> master, origin/master, origin/HEAD)
    Author: Ben Dover <noone@overthewire.org>
    Date:   Sun Apr 23 18:04:42 2023 +0000

    initial commit of README.md

    diff --git a/README.md b/README.md
    new file mode 100644
    index 0000000..029ba42
    --- /dev/null
    +++ b/README.md
    @@ -0,0 +1 @@
    +just an epmty file... muahaha
    ```
- We pay attention to branches: Check how many branches are there: `git branch` -> List branches.
  ```sh
  * master
  ```
- We are now at master branch, so we use another way: `git tag` -> show hidden things.
- There is a hidden commit: `secret` -> `git show secret`. -> `OoffzGDlzhAlerFJ2cAiz1D41JW1Mhmt`
###
### III. Result:
The password for next level: `OoffzGDlzhAlerFJ2cAiz1D41JW1Mhmt`

[Bandit_Level31]: <https://overthewire.org/wargames/bandit/bandit31.html>
