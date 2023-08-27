# ![](https://overthewire.org/img/domokitten.png)

# Bandit_Level3

## Source: <https://overthewire.org/wargames/bandit/bandit3.html>

### I. Connect: 

`ssh -p 2220 bandit2@bandit.labs.overthewire.org`
Password: `rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi`
### II. My solution:
- To solve this level, firstly find in home directory file which has name longer than "spaces"
  - `find /home -type f -name spaces\* 2>/dev/null`

- Read the file, using cat command
  - `cat /home/bandit2/spaces\ in\ this\ filename`

### III. Result:
Password for next level: `aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG`