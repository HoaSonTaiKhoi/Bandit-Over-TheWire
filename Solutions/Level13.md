# ![](https://overthewire.org/img/domokitten.png)

# Bandit_Level13

## Source: <https://overthewire.org/wargames/bandit/bandit13.html>

###

### I. Connect:
- 'ssh -p 2220 bandit12@bandit.labs.overthewire.org'
- Password: `JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv`

###
### II. My solution:
- Create a new directory in /tmp: `mkdir /tmp/my_file`
- Copy data.txt to that directory: `cp data.txt /tmp/my_file`
- And `cd /tmp/my_file`
- Because data.txt is a hex-dump file, firstly decoding it: `xxd -r data.txt > data_out`
1. Check file format: `file data_out` -> data_out is an gzip file.
   - Rename `data_out`: `mv data_out data.gz`
   - Unzip it: `gzip -d data.gz` -> obtain new file:`data`
####
2. Check file format: `file data` -> data is a bzip2 file.
   - Unzip it: `bzip2 -d data` -> obtain `data.out`
####
3. Check file formar: `file data.out` -> a gzip file
   - Rename `data.out`: `mv data.out data.gz`
   - Unzip it: `gzip -d data.gz` -> obtain `data`
####
4. Check file format: `file data` -> a POSIX tar archive file
   - Rename `data`: `mv data data.tar`
   - Unzip it: `tar -xvf data.tar` -> obtain `data5.bin`
####
5. Check file format: `file data5.bin` -> a POSIX tar archive file
   - Rename `data5.bin`: `mv data5.bin data5.tar`
   - Unzip it: `tar -xvf data5.tar` -> obtain `data6.bin`
####
6. Check file format: `file data6.bin` -> a bzip2 file
   - Unzip it: `bzip2 -d data6.bin` -> obtain `data6.bin.out`
####
7. Check file format: `file data6.bin.out` -> a POSIX tar archive file
   - Rename `data6.bin.out`: `mv data6.bin.out data6.tar`
   - Unzip it: `tar -xvf data6.tar` -> obtain `data8.bin`
####
8. Check file format: `file data8.bin` -> a gzip file
   - Rename `data8.bin`: `mv data8.bin data8.gz`
   - Unzip it: `gzip -d data8.gz` -> obtain `data8`
####
9. Check file format: `file data8` -> a .txt file

- Read the data8: `cat data8`
###

### III. Result:
Password for next level: `wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw`