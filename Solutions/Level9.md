# ![](https://overthewire.org/img/domokitten.png)

# Bandit_Level9

## Source: <https://overthewire.org/wargames/bandit/bandit9.html>

### I. Connect:
- 'ssh -p 2220 bandit8@bandit.labs.overthewire.org'
- Password: `TESKZC0XvTetK0S9xNwm25STk5iWrBvP`

### II. My solution:
- `sort` command help us sort rows in file.
- `uniq` command help us identify how many times the line was repeated.
- We can use `sort data.txt | uniq -c` to figure out how many unrepeated line and how many times each line was repeated.
- Moreover, we can use `sort data.txt | uniq -u` to directly find the line that appear only once.

### III. Result:
Password for next level: `EN632PlfYiZbn3PhVK3XOGSlNInNE00t`