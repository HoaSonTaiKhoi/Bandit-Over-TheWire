# ![](https://overthewire.org/img/domokitten.png)

# Bandit_Level7

## Source: <https://overthewire.org/wargames/bandit/bandit7.html>

### I. Connect:
- 'ssh -p 2220 bandit6@bandit.labs.overthewire.org'
- Password: `P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU`

### II. My solution:
- To find files stored somewhere in the server with special requires,
  - 33c bytes in size:  `-size 33c`
  - owned by user bandit7: `-user bandit7`
  - owned by group bandit6: `-group bandit6`
###
- Answer: `find / -type f -size 33c -user bandit7 -group bandit6`
###
- But the output has so many error answers so we temporarily put error cases in /dev/null:
  - `find / -type f -size 33c -user bandit7 -group bandit6 2>/dev/null`
###
- Result: `/var/lib/dpkg/info/bandit7.password`
  - Read file: `cat /var/lib/dpkg/info/bandit7.password`
###
 

### III. Result:
Password for next level: `z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S`