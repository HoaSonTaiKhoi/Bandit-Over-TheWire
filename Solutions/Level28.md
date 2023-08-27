# ![](https://overthewire.org/img/domokitten.png)

# Bandit_Level28

## Source:
- [Bandit_Level28] - The topic of Bandit, Level28.
- [Git Clone] - Using git clone to back up data.
###
### I. Connect:
```sh
ssh -p 2220 bandit27@bandit.labs.overthewire.org
Password: YnQpBuifNMas1hcUFk70ZmqkhUU2EuaS
```
###
### II. My solution:
- To pass this level, we need data from bandit27's repository.
- Create a temporily file: `mkdir /tmp/git_tmp` then `cd /tmp/git_tmp`.
- Use `git clone` command with ssh_link: `git clone ssh://<user>@<host><:2220>/path/repo`
> Answer: `git clone ssh://bandit27-git@localhost:2220/home/bandit27-git/repo`.

- After that, a new directory appear in git_tmp directory: `repo`
- `cd repo`
- Check directory: `ls`. -> There are a file named `README`.
- Check file format of `README`: `file README` -> ASCII text.
- Read it: `cat README`
```sh   
The password to the next level is: AVanL161y9rsbcJIsFHuw35rjaOM19nR
```
###
### III. Result:
The password for next level: `AVanL161y9rsbcJIsFHuw35rjaOM19nR`

[Bandit_Level28]: <https://overthewire.org/wargames/bandit/bandit28.html>
[Git Clone]: <https://linuxhint.com/git_clone_command/>