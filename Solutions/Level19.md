# ![](https://overthewire.org/img/domokitten.png)

# Bandit_Level19

## Source: <https://overthewire.org/wargames/bandit/bandit19.html>

###

### I. Connect:
- `ssh -p 2220 bandit18@bandit.labs.overthewire.org` 
- Password: `hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg`
###
### II. My solution:
- In this level, we can't normally login to bandit18, after connecting, the session end immediately (.bashrc).

- So we use usual command with `ssh` command: `ssh -p 2220 bandit18@bandit.labs.overthewire.org ls`
  - `ls` help list which are in bandit18 directory.
####
- Output: `readme`.

- Logout again, so `ssh -p 2220 bandit18@bandit.labs.overthewire.org cat readme`.
###
### III. Result:
Password for next level: `awhqfNnAbc1naukrpqDYcF95h7HoMTrC`