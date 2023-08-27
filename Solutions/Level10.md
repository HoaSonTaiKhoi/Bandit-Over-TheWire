# ![](https://overthewire.org/img/domokitten.png)

# Bandit_Level10

## Source: <https://overthewire.org/wargames/bandit/bandit10.html>

### I. Connect:
- 'ssh -p 2220 bandit9@bandit.labs.overthewire.org'
- Password: `EN632PlfYiZbn3PhVK3XOGSlNInNE00t`

### II. My solution:
- To find human-readable strings in a file, we use `strings` command.
  - `strings data.txt`
###
- But the output has lots of human-readable strings.
- However, we have given information: `preceded by several ‘=’ characters`
  - Add `grep "="` to obtain lines in output that contain "="
###
- The final answer: `strings data.txt | grep "="`
- Now we can see a line in output that is similar to previous passwords: `========== G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s`

### III. Result:
Password for next level: `G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s`