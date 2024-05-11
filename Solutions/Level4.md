# ![](https://overthewire.org/img/domokitten.png)

# Bandit_Level 4

## Source: <https://overthewire.org/wargames/bandit/bandit4.html>

### I. Connect:
- 'ssh -p 2220 bandit3@bandit.labs.overthewire.org'
- Password: `aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG`

### II. My solution:
- Find "inhere" folder
  - `ls` or `find -type d -name inhere`

- Go into "inhere" directory
  - `cd ./inhere`

- Find hidden file
  - `ls -a`
  - `cat .\hidden`
 
### III. Result:
Password for next level: `2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe`