# ![](https://overthewire.org/img/domokitten.png)

# Bandit_Level17

## Source: <https://overthewire.org/wargames/bandit/bandit17.html>

###

### I. Connect:
- `ssh -p 2220 bandit16@bandit.labs.overthewire.org` 
- Password: `JQttfApK4SeyHwDlI9SXGR50qclOAil1`

###
### II. My solution:
- To find the open port, we use `netcat` command or `nmap` command
  - `nc`- netcat: 
    - flag '-z' help `netcat` only scan for open ports without sending any data to them.
    - flag '-v' provide more verbose information.
  - `nmap` can scan for open ports in localhost-`bandit.labs.overthewire.org`
####
- Source:
  - <https://linuxize.com/post/netcat-nc-command-with-examples/>
  - <https://linuxhint.com/use-nmap-command-ubuntu/>
####
- Answer_1: `nc -zv localhost 31000-32000 2>&1 | grep "succeeded"`.
  - `2>&1` redirect all of standard errors to standard output.
  - `grep "succeeded"` choose the line that have "succeeded". It also mean that port is an open port.
####
- Answer_2: `nmap bandit.labs.overthewire.org -p31000-32000`.
####
- After "Enter" Answer_1:
  - Connection to localhost (127.0.0.1) 31046 port [tcp/*] succeeded!
  - Connection to localhost (127.0.0.1) 31518 port [tcp/*] succeeded!-
  - Connection to localhost (127.0.0.1) 31691 port [tcp/*] succeeded!
  - Connection to localhost (127.0.0.1) 31790 port [tcp/*] succeeded!
  - Connection to localhost (127.0.0.1) 31960 port [tcp/*] succeeded!
####
- After "Enter" Answer_2:
  | PORT | STATE | SERVICE |
  |-----------|:--------:|:---------:|
  | 31046/tcp | open | unknown |
  | 31518/tcp | open | unknown |
  | 31691/tcp | open | unknown |
  | 31790/tcp | open | unknown |
  | 31960/tcp | open | unknown |

####
- Test:
  - `openssl s_client -connect localhost:31046` -> nothing.
  - `openssl s_client -connect localhost:31518` -> simply return what we send to it.
  - `openssl s_client -connect localhost:31691` -> nothing
  - `openssl s_client -connect localhost:31790` -> return rsa_key when we send previous password to it.
  - `openssl s_client -connect localhost:31960` -> nothing.
####
- `mkdir /tmp/ssh_file` : create a new directory in `tmp` directory.

- In `ssh_file` directory, I save rsa-key received in port `31790` in `sshkey_17.private`.

- Change permission of `sshkey_17.private` into `700` - just user own it can read, write and execute - "private" rsa-key.

- Using `ssh` command with `-i` flag to import rsa_key while login into the next level-bandit17.

- Answer: `ssh -p 2220 -i sshkey_17.private bandit17@bandit.labs.overthewire.org`.

- Read password to login to bandit17: `cat /etc/bandit_pass/bandit17`.
###
### III. Result:
Password for next level: `VwOSWtCA7lRKkTfbr2IDh6awj9RNZM5e`