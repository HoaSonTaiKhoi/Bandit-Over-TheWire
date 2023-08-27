# ![](https://overthewire.org/img/domokitten.png)

# Bandit_Level8

## Source: <https://overthewire.org/wargames/bandit/bandit8.html>

### I. Connect:
- 'ssh -p 2220 bandit7@bandit.labs.overthewire.org'
- Password: `z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S`

### II. My solution:
- To find the password next to "millionth" in data.txt, we use `grep`.
- Answer: `grep "millionth" data.txt`
  - In this case, output is a row that contain the word "millionth" and the password next to it.

### III. Result:
Password for next level: `TESKZC0XvTetK0S9xNwm25STk5iWrBvP`