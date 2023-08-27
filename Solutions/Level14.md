# ![](https://overthewire.org/img/domokitten.png)

# Bandit_Level14

## Source: <https://overthewire.org/wargames/bandit/bandit14.html>

###

### I. Connect:
- 'ssh -p 2220 bandit13@bandit.labs.overthewire.org'
- Password: `wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw`

###
### II. My solution:
- To login to user bandit14, we use `ssh -i <key-rsa> <user_name>@<server>`.
- Using `ls -l` we can see the file "sshkey.private" has permissions `-rw-r-----` that means 640 or the owner(bandit13) can read and write, and bandit13's group can just read. -> So sshkey.private is a public rsa_key.
- Answer: `ssh -p 2220 -i sshkey.private bandit14@bandit.labs.overthewire.org` then type: `yes`.
- We've already login to user bandit14 and to find password for level 14: `cat /etc/bandit_pass/bandit14`.

###
### III. Result:
Password for next level: `fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq`