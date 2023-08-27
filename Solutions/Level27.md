# ![](https://overthewire.org/img/domokitten.png)

# Bandit_Level27

## Source:
- [Bandit_Level27] - The topic of Bandit, Level27.
- [Shell] - Shell theory.
- [Vim] - Vim editor.
###
### I. Connect:
```sh
ssh -p 2220 bandit26@bandit.labs.overthewire.org
Password: c7GvcKlw9mC7aUQaPx7nwFstuAIBw1o1
```
###
### II. My solution:
- At previous level: when we login into bandit26 normally, we wil be logged out immediately.
- Therefore, we still do simmilarly level26.
- When open the terminal window, we resize it with the shortened height.
- Then we normally login again:
![](https://scontent.fsgn5-12.fna.fbcdn.net/v/t1.15752-9/370543497_538657655067352_439233171257517828_n.png?_nc_cat=103&ccb=1-7&_nc_sid=aee45a&_nc_ohc=j8FmsYv-XoIAX_-Y8dI&_nc_ht=scontent.fsgn5-12.fna&oh=03_AdR8BVeIUxyDf_xHyb6GGO7mixgS73yjbkzJ-cWqrHPJjw&oe=65115E79)
####
- Type to acess to `vim editor`.To use:
  - With command: `:!<command>`.
  - With cat: `:e cat <file's directory>`.
  - With setting shell: `:set shell=<new shell's directory>`.

- To use command, we must change the bandit26's shell: `:set shell=/bin/bash`, check: `:set shell ?`.

- Check if there are any files?: `:!ls -la`.
```sh
total 44
drwxr-xr-x  3 root     root      4096 Apr 23 18:04 .
drwxr-xr-x 70 root     root      4096 Apr 23 18:05 ..
-rw-r--r--  1 root     root       220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root     root      3771 Jan  6  2022 .bashrc
-rw-r--r--  1 root     root       807 Jan  6  2022 .profile
drwxr-xr-x  2 root     root      4096 Apr 23 18:04 .ssh
-rwsr-x---  1 bandit27 bandit26 14876 Apr 23 18:04 bandit27-do
-rw-r-----  1 bandit26 bandit26   258 Apr 23 18:04 text.txt
```
-We can see `bandit27-do` has onwer is bandit27 and check its format: `:!file bandit27-do`
```sh
bandit27-do: setuid ELF 32-bit LSB executable, Intel 80386, version 1 (SYSV), dynamically linked, interpreter /lib/ld-linux.so.2, BuildID[sha1]=c148b21f7eb7e816998f07490c8007567e51953f, for GNU/Linux 3.2.0, not stripped
```
- `bandit27-do` is a setuid file.
- So we can use this to find bandit27's password: `!./bandit27-do cat /etc/bandit_pass/bandit27`.
###
### III. Result:
The password for next level: `YnQpBuifNMas1hcUFk70ZmqkhUU2EuaS`

[Bandit_Level27]: <https://overthewire.org/wargames/bandit/bandit27.html>
[Shell]: <https://viblo.asia/p/gioi-thieu-ve-linux-shell-va-shell-script-aWj53LweK6m>
[Vim]: <https://blog.kdata.vn/cach-su-dung-vim-trong-linux-lenh-vim-trong-linux-8028/>