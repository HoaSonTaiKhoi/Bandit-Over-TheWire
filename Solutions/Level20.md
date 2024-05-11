# ![](https://overthewire.org/img/domokitten.png)

# Bandit_Level20

## Source: <https://overthewire.org/wargames/bandit/bandit20.html>

###
### I. Connect:
- `ssh -p 2220 bandit19@bandit.labs.overthewire.org` 
- Password: `awhqfNnAbc1naukrpqDYcF95h7HoMTrC`

###
### II. My solution:
- Check detail of bandit20-do: `stat -c "%a %A %U %G" bandit20-do`.
- Output: `4750 -rwsr-x--- bandit20 bandit19`

####
- We can infer that:
  - `4750` that mean bandit20-do is an setuid file(not SGID).
  - `-rwsr-x---` mean owner can full acess to bandit20-do, group own it just can read and execute it.
  - `bandit20` user owning it is bandit20.
  - `bandit19` group bandit19 can acess to it.
####
- Then we check group of user `bandit19`:
  - `cat /etc/group | grep bandit19` check group bandit19. -> `bandit19:x:11019:`
  - `cat /etc/passwd | grep bandit19` check user bandit19. 
  > `bandit19:x:11019:11019:bandit level 19:/home/bandit19:/bin/bash`
####
- Therefore, user bandit19 can execute bandit20-do.
- `./bandit20-do ls /etc/bandit_pass`: list files and folders in bandit_pass.
- `./bandit20-do cat /etc/bandit_pass/bandit20`: read bandit20.
####
### III. Result:
Password for next level: `VxCazJaVykI6W36BkBU0mJTCM8rR95XT`