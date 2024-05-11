# ![](https://overthewire.org/img/domokitten.png)

# Bandit_Level21

## Source: <https://overthewire.org/wargames/bandit/bandit21.html>

###
### I. Connect:
- `ssh -p 2220 bandit20@bandit.labs.overthewire.org` 
- Password: `VxCazJaVykI6W36BkBU0mJTCM8rR95XT`

###
### II. My solution:
- To pass this level, firstly we create an temp port included password of previous level.
####
- Answer: `echo -n "VxCazJaVykI6W36BkBU0mJTCM8rR95XT" | nc -l -p 9999&`.
  - `echo` command help put ola password into temp port.
  - `-n` prevent echo from creating a new line while input.
  - In `nc` command:
    - `-l`: listen-help netcat listen a temp port, aim to transport file.
    - `-p`: port.
    - `&`: help the process run in the background.
####
- Output:   `[1] 529381`.

- Then connect `suconnect` with temp port `9999` created on netcat. `echo` command help the password auto sent to `suconnect`.
- Answer: `./suconnect 9999`.
### 
### III. Result:
Password for next level: `NvEJF7oVjkddltPSrdKEFOllh9V1IBcq`