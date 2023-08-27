# ![](https://overthewire.org/img/domokitten.png)

# Bandit_Level30

## Source:
- [Bandit_Level30] - The topic of Bandit, Level30.
- [Git Branch] - Git Branch Usability.
###
### I. Connect:
```sh
ssh -p 2220 bandit29@bandit.labs.overthewire.org
Password: tQKvmcwNYcFS6vmPHIUSI3ShmsrQZK8S
```
###
### II. My solution:
- Similar to previous level, firstly create a temporarily directory: `mkdir /tmp/git_29` then `cd /tmp/git_29`
- In git_29 directory: `git clone ssh://bandit29-git@localhost:2220/home/bandit29-git/repo`
- Type `yes` and enter the bandit29's password.
- Check `git_29` directory: `ls` then `cd repo`
- In `repo` directory:
  - `ls` -> There is a markdown file `README.md` -> Read it: `cat README.md`:
    ```sh
    # Bandit Notes
    Some notes for bandit30 of bandit.

    ## credentials

    - username: bandit30
    - password: <no passwords in production!>
    ```
  - Check commit: `git log`:
    ```sh
    commit 4bd5389f9f2b9e96ba517aa751ee58d051905761 (HEAD -> master, origin/master, origin/HEAD)
    Author: Ben Dover <noone@overthewire.org>
    Date:   Sun Apr 23 18:04:40 2023 +0000

    fix username

    commit 1a57cf10158f133c4f40ff82251f605a7618631d
    Author: Ben Dover <noone@overthewire.org>
    Date:   Sun Apr 23 18:04:40 2023 +0000

    initial commit of README.md
    ```
  - Show commit: `git show 4bd5389f9f2b9e96ba517aa751ee58d051905761` and `git show 1a57cf10158f133c4f40ff82251f605a7618631d`:
    ```sh
    commit 4bd5389f9f2b9e96ba517aa751ee58d051905761 (HEAD -> master, origin/master, origin/HEAD)
    Author: Ben Dover <noone@overthewire.org>
    Date:   Sun Apr 23 18:04:40 2023 +0000

    fix username

    diff --git a/README.md b/README.md
    index 2da2f39..1af21d3 100644
    --- a/README.md
    +++ b/README.md
    @@ -3,6 +3,6 @@ Some notes for bandit30 of bandit.

    ## credentials

    -- username: bandit29
    +- username: bandit30
    - password: <no passwords in production!>
    ```
    
    ```sh
    commit 1a57cf10158f133c4f40ff82251f605a7618631d
    Author: Ben Dover <noone@overthewire.org>
    Date:   Sun Apr 23 18:04:40 2023 +0000

    initial commit of README.md

    diff --git a/README.md b/README.md
    new file mode 100644
    index 0000000..2da2f39
    --- /dev/null
    +++ b/README.md
    @@ -0,0 +1,8 @@
    +# Bandit Notes
    +Some notes for bandit30 of bandit. 
    +
    +## credentials
    +
    +- username: bandit29
    +- password: <no passwords in production!>
    ```
- There is no password in repo, why?
- We pay attention to branches: Check how many branches are there: `git branch` -> List branches.
  ```sh
  * master
  remotes/origin/HEAD -> origin/master
  remotes/origin/dev
  remotes/origin/master
  remotes/origin/sploits-dev
  ```
- Present branch is HEAD, change branch to dev: `git checkout dev`
- Check files in branch `dev`:
  ```sh
  code  README.md
  ```
- Read README.md: `cat README.md`
  ```sh
  # Bandit Notes
  Some notes for bandit30 of bandit.

  ## credentials

  - username: bandit30
  - password: xbhV3HpNGlTIdnjUrdAlPzc2L6y9EOnS

  bandit29@bandit:/tmp/git_29/repo$ cat README.md
  # Bandit Notes
  Some notes for bandit30 of bandit.

  ## credentials

  - username: bandit30
  - password: xbhV3HpNGlTIdnjUrdAlPzc2L6y9EOnS
  ```
###
### III. Result:
The password for next level: `xbhV3HpNGlTIdnjUrdAlPzc2L6y9EOnS`

[Bandit_Level30]: <https://overthewire.org/wargames/bandit/bandit30.html>
[Git Branch]: <https://www.atlassian.com/git/tutorials/using-branches>
