# ![](https://overthewire.org/img/domokitten.png)

# Bandit_Level11

## Source: 
### <https://overthewire.org/wargames/bandit/bandit11.html>
### <https://en.wikipedia.org/wiki/Base64>

###

### I. Connect:
- 'ssh -p 2220 bandit10@bandit.labs.overthewire.org'
- Password: `G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s`

###
### II. My solution:
- `base64` command can convert normal document (8-bit) to a 6-bit string.
- `base64 -d` can decode a 6-bit document to normal document(ASCII or 8-bit).
- In this case we use `base64 -d data.txt`.

###

### III. Result:
Password for next level: `6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM`