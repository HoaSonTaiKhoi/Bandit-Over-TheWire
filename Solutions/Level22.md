# ![](https://overthewire.org/img/domokitten.png)

# Bandit_Level22

## Source:
- [Bandit_Level22] - The topic of Bandit, Level22.
- [Crontab] - Thoery about cron and cronjob.
### I. Connect:
```sh
ssh -p 2220 bandit21@bandit.labs.overthewire.org
Password: NvEJF7oVjkddltPSrdKEFOllh9V1IBcq
```
###
### II. My Solution:
- Change directory: `cd /etc/cron.d` ; Check how many files are there: `ls`.

- We can see the file `cronjob_bandit22`, check its format: `file cronjob_bandit22` -> ASCII text.
- Read it: `cat cronjob_bandit22` -> Output:
```sh
@reboot bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null
* * * * * bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null
```
####
- We can see executable file cronjob_bandit22.sh routinely transmiting data into /dev/null.

- Check `cronjob_bandit22` format: `file /usr/bin.cronjob_bandit22.sh` -> ASCII text and executable file.

- Read it: `cat /usr/bin/cronjob_bandit22.sh` ->Output:
```sh
#!/bin/bash
chmod 644 /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
cat /etc/bandit_pass/bandit22 > /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
```
####
- Password in `/etc/bandit_pass/bandit22` is transmited into `/tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv` routinely.

- Read that tmp_file: `cat /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv`

- We finally found the password for next level: `WdDozAdTM2z9DiFEQ2mGlwngMfj4EZff`

###
### III. Result:
Password for next level: `WdDozAdTM2z9DiFEQ2mGlwngMfj4EZff`


[Bandit_Level22]: <https://overthewire.org/wargames/bandit/bandit22.html>
[Crontab]: <https://vietnix.vn/crontab/>