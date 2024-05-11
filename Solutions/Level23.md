# ![](https://overthewire.org/img/domokitten.png)

# Bandit_Level23

## Source:
- [Bandit_Level23] - The topic of Bandit, Level23.
- [Crontab] - Thoery about cron and cronjob.
### I. Connect:
```sh
ssh -p 2220 bandit22@bandit.labs.overthewire.org
Password: WdDozAdTM2z9DiFEQ2mGlwngMfj4EZff
```
###
### II. My Solution:
- Simmilar to Level22, Read `cronjob_bandit23`: `cat cronjob_bandit23` -> Output:
```sh
@reboot bandit23 /usr/bin/cronjob_bandit23.sh  &> /dev/null
* * * * * bandit23 /usr/bin/cronjob_bandit23.sh  &> /dev/null
```

####
- We can see executable file cronjob_bandit22.sh routinely transmiting data into /dev/null.

- Check `cronjob_bandit22` format: `file /usr/bin.cronjob_bandit23.sh` -> ASCII text and executable file.

- Read it: `cat /usr/bin/cronjob_bandit23.sh` -->Output:
```sh
#!/bin/bash

myname=$(whoami)
mytarget=$(echo I am user $myname | md5sum | cut -d ' ' -f 1)

echo "Copying passwordfile /etc/bandit_pass/$myname to /tmp/$mytarget"

cat /etc/bandit_pass/$myname > /tmp/$mytarget
```

####
- In file `cronjob_bandit23`:
  - `myname=$(whoami)`: Variable `myname` save the output of whoami command and whoami command is executed by user bandit23 so myname="bandit23". 
  ####
  - `mytarget=$(echo I am user $myname | md5sum | cut -d ' ' -f 1)`
    - `mytarget` save the output of echo.
    - `md5sum` : verify data integrity
    - `cut -d ' ' -f 1`: get the first word delimited by ' ' in the string encoded by md5sum.
  ####
  - `cat /etc/bandit_pass/$myname > /tmp/$mytarget` --> the file having name saved by target is the password file.
####
- I run the command: `echo I am user bandit23 | md5sum | cut -d ' ' -f 1`
Therefore, mytarget=`8ca319486bfbbc3663ea0fbe81326349`

- Read password: `cat /tmp/8ca319486bfbbc3663ea0fbe81326349`
###
### III. Result:
Password for next level: `QYw0Y2aiA672PsMmh9puTQuhoz8SyR2G`


[Bandit_Level23]: <https://overthewire.org/wargames/bandit/bandit22.html>
[Crontab]: <https://vietnix.vn/crontab/>