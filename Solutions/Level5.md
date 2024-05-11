# ![](https://overthewire.org/img/domokitten.png)

# Bandit_Level 5

## Source: <https://overthewire.org/wargames/bandit/bandit5.html>

### I. Connect:
- 'ssh -p 2220 bandit4@bandit.labs.overthewire.org'
- Password: `2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe`

### II. My solution:
- Go into "inhere" directory
  - `cd ./inhere`
- When using `ls -a`, we can't distinguish which we need.
- So I use `find -type f | xargs file | grep ASCII`, in which
  - `find -type f` help find files (not directory).
  - `xargs file` list format of found files.
  - `grep ASCII` filter out files which are human-readable files.
- Read the ASCII text file
  - `cat ./-file07` 
 
### III. Result:
Password for next level: `lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR`