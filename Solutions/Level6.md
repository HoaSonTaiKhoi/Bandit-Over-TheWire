# ![](https://overthewire.org/img/domokitten.png)

# Bandit_Level6

### Source: <https://overthewire.org/wargames/bandit/bandit6.html>

### I. Connect:
- 'ssh -p 2220 bandit5@bandit.labs.overthewire.org'
- Password: `lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR`

### II. My solution:
- Go into "inhere" directory
  - `cd ./inhere`
- To find files with special requires,
  - 1033c bytes in size:  `-size 1033c`
  - not executable: `! -executable`
  - human readable: `xargs file` or `-exec file {} +` and `grep text` or `grep ASCII`
- In summary, we can type in two ways:
  - `find -type f -size 1033c ! -executable | xargs file | grep text`.
  - `find -type f -size 1033c ! -executable -exec file {} + | grep text`.

- Read the ASCII text file
  - `cat ./maybehere07/.file2`
 
### III. Result:
Password for next level: `P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU`