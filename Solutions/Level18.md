# ![](https://overthewire.org/img/domokitten.png)

# Bandit_Level18

## Source: <https://overthewire.org/wargames/bandit/bandit18.html>

###

### I. Connect:
- In the previos level, we've already login to bandit17, or we can login with password.
- `ssh -p 2220 bandit17@bandit.labs.overthewire.org`  Password: `VwOSWtCA7lRKkTfbr2IDh6awj9RNZM5e`
###
### II. My solution:
- To find the difference between `passwords.old` and `passwords.new`, we use `diff` command.
- Answer: `diff passwords.old passwords.new`

- Output: 
  > `42c42`
  
  > `< hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg`
  
  > `> glZreTEH1V3cGKL6g4conYqZqaEj0mte`
####
- There is another important information is that `The password for the next level is in passwords.new`

####
- We start to compare which of two ouputs is in the passwords.new.
  - `cat passwords.new | grep hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg` -> the first one is bandit18's password.
  - `cat passwords.new | grep glZreTEH1V3cGKL6g4conYqZqaEj0mte` -> this one is not bandit18's password.
###
### III. Result:
Password for next level: `hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg`