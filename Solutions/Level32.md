# ![](https://overthewire.org/img/domokitten.png)

# Bandit_Level32

## Source:
- [Bandit_Level32] - The topic of Bandit, Level32.
###
### I. Connect:
```sh
ssh -p 2220 bandit31@bandit.labs.overthewire.org
Password: OoffzGDlzhAlerFJ2cAiz1D41JW1Mhmt
```
###
### II. My solution:
- Similar to previous level, firstly create a temporarily directory: `mkdir /tmp/git_32` then `cd /tmp/git_32`
- In git_32 directory: `git clone ssh://bandit31-git@localhost:2220/home/bandit31-git/repo`
- Type `yes` and enter the bandit30's password.
- Check `git_32` directory: `ls` then `cd repo`
- In `repo` directory:
  - `ls` -> There is a markdown file `README.md` -> Read it: `cat README.md`:
    ```sh
    This time your task is to push a file to the remote repository.

    Details:
    File name: key.txt
    Content: 'May I come in?'
    Branch: master
    ```
####
- Create a new text file with: "May I come in?": `echo 'May I come in?' > key.txt`.
- Use `git add`: `git add key.txt`, but:
  ```sh
  The following paths are ignored by one of your .gitignore files:
  key.txt
  hint: Use -f if you really want to add them.
  hint: Turn this message off by running
  hint: "git config advice.addIgnoredFile false"
  ```
####
- Because `.gitignore` prevent to normally git add. Therefore, add flag `-f` -> `git add -f key.txt`
- Commit: `git commit -m "May I come in?"`
- Check branches: `git branch` -> There is one branch `master` -> Currently at `master`.
- Push: `git push -u origin master`.
```sh
Enumerating objects: 7, done.
Counting objects: 100% (7/7), done.
Delta compression using up to 2 threads
Compressing objects: 100% (4/4), done.
Writing objects: 100% (6/6), 529 bytes | 264.00 KiB/s, done.
Total 6 (delta 1), reused 0 (delta 0), pack-reused 0
remote: ### Attempting to validate files... ####
remote:
remote: .oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.
remote:
remote: Well done! Here is the password for the next level:
remote: rmCBvG56y58BXzv98yZGdO7ATVL5dW8y
remote:
remote: .oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.
remote:
remote:
remote: .oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.
remote:
remote: Wrong!
remote:
remote: .oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.
remote:
To ssh://localhost:2220/home/bandit31-git/repo
 ! [remote rejected] master -> master (pre-receive hook declined)
error: failed to push some refs to 'ssh://localhost:2220/home/bandit31-git/repo
```
###
### III. Result:
The password for next level: `rmCBvG56y58BXzv98yZGdO7ATVL5dW8y`

[Bandit_Level32]: <https://overthewire.org/wargames/bandit/bandit32.html>
