# ![](https://overthewire.org/img/domokitten.png)

# Bandit_Level2

## Source: <https://overthewire.org/wargames/bandit/bandit2.html>

### I. Connect: 

`ssh -p 2220 bandit1@bandit.labs.overthewire.org`
Password: `NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL`
### II. My solution:
- To solve this level, first find in home directory file which has name "-" or longer
  - `find /home -name -\*`

- There are a lot of results, so I add "2>/dev/null" to temporarily put error answers to /dev/null
  - `find /home -name -\* 2>/dev/null`

- Read the file, using cat command
  - `cat /home/bandit1/-`

### III. Result:
Password for next level: `rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi`