# ![](https://overthewire.org/img/domokitten.png)

# Bandit_Level12

## Source: <https://overthewire.org/wargames/bandit/bandit12.html>

###

### I. Connect:
- 'ssh -p 2220 bandit11@bandit.labs.overthewire.org'
- Password: `6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM`

###
### II. My solution:
- Because, all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions, so
  - a, z become n, m => lowercase n-z; a-m
  - A, Z become N, M => uppercase N-Z; A-M
- In this case, we can use `cat data.txt` and `tr` command:
  - `cat data.txt | tr A-Za-z N-ZA-Mn-za-m`
###

### III. Result:
Password for next level: `JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv`