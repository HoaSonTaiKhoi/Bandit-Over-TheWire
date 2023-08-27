# ![](https://overthewire.org/img/domokitten.png)

# Bandit_Level26

## Source:
- [Bandit_Level26] - The topic of Bandit, Level26.
- [Shell] - Shell theory.
### I. Connect:
```sh
ssh -p 2220 bandit25@bandit.labs.overthewire.org
Password: p7TaowMYrmu23Ol8hiZh9UvD0O9hpx8d
```

### II. My solution:
- Because tips for this level is two few, so I check the default shell of bandit25: `ls`
- There is a RSA-key file: `bandit26.sshkey`
- So I test to login to bandit26 with it: `ssh -i bandit26.sshkey bandit26@bandit.labs.overthewire.org`.
- But I was logged out immediately.
- Then I check the file `passwd` in `/etc`: `cat /etc/passwd`.
- I saw that other users has a default shell is `/bin/bash` except bandit26: `cat /etc/passwd | grep bandit26`.
```sh
bandit26:x:11026:11026:bandit level 26:/home/bandit26:/usr/bin/showtext
```
- bandit26's shell is /usr/bin/showtext, I read it: `cat /usr/bin/showtext`.
```sh
#!/bin/sh

export TERM=linux

exec more ~/text.txt
exit 0
```

- `more` command: When the cursor drags to the end of the file, it will not be able to pull up to read again, then `exit 0` will do the task of exiting the login session of bandit26.
- Therefore, when we set the Cygwin64 window in normal scale: the cursor is immediately at the end of the file, `exit 0` is called.
- To fix this problem, we adjust the Cygwin64 terminal window scale to small size, like this:
![](https://scontent.fsgn5-3.fna.fbcdn.net/v/t1.15752-9/370055000_293696276642690_4885717500627121973_n.png?_nc_cat=104&ccb=1-7&_nc_sid=ae9488&_nc_ohc=jY4rlgdTWEUAX823hKy&_nc_ht=scontent.fsgn5-3.fna&oh=03_AdRJX0QZSgp_UYHwXpH4QJe9JONyNQlI2RtLw_YeGvwb0A&oe=6511542A)
- Then login to bandit26: `ssh -i bandit26.sshkey bandit26@bandit.labs.overthewire.org`
- Type `v` to enable `vim` command.
- Finally, type: `:e cat /etc/bandit_pass/bandit26`.
###
### III. Result:
The password for next level: `c7GvcKlw9mC7aUQaPx7nwFstuAIBw1o1`