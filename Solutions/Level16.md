# ![](https://overthewire.org/img/domokitten.png)

# Bandit_Level16

## Source: <https://overthewire.org/wargames/bandit/bandit16.html>

###

### I. Connect:
- `ssh -p 2220 bandit15@bandit.labs.overthewire.org` 
- Password: `jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt`

###
### II. My solution:
- To get the password for next level, we use `openssl` command.
- `openssl s_client -connect localhost:30001`.
  - `s_client` command is an helpful test client for troubleshooting remote SSL or TLS connections.
  - flag `-connect` help return ssl handshake
- Copy and Paste the previous-level password: `jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt` then press Enter.
###
### III. Result:
Password for next level: `JQttfApK4SeyHwDlI9SXGR50qclOAil1`