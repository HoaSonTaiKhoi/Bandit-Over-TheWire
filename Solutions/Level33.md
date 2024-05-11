# ![](https://overthewire.org/img/domokitten.png)

# Bandit_Level33

## Source:
- [Bandit_Level33] - The topic of Bandit, Level33.
###
### I. Connect:
```sh
ssh -p 2220 bandit32@bandit.labs.overthewire.org
Password: rmCBvG56y58BXzv98yZGdO7ATVL5dW8y
```
###
### II. My solution:
- To use command mode, type `$0`.

- check the user: `whoami` -> bandit33.
- We can read password file: `cat /bandit_pass/bandit23` -> `odHo63fHiFqcWWJG9rLiLDtPm45KzUKy`.
- Exit user bandit32.
- Login to bandit33: `ssh -p 2220 bandit33@bandit.labs.overthewire.org`, Password: `odHo63fHiFqcWWJG9rLiLDtPm45KzUKy`
- Check: `ls` -> README.txt
- Read it: `cat README.txt`:
```sh
Congratulations on solving the last level of this game!

At this moment, there are no more levels to play in this game. However, we are constantly working
on new levels and will most likely expand this game with more levels soon.
Keep an eye out for an announcement on our usual communication channels!
In the meantime, you could play some of our other wargames.

If you have an idea for an awesome new level, please let us know!
```
###
### III. Result:
END!

[Bandit_Level33]: <https://overthewire.org/wargames/bandit/bandit33.html>
