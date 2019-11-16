# Bandit 17

## Problem Information 
  > There are 2 files in the homedirectory: passwords.old and passwords.new. The password for the next level is in passwords.new and is the only line that has been changed between passwords.old and passwords.new

## Solution
 Connect using the previous certificate saved as a file. `ssh -i sshkey.private bandit17@bandit.labs.overthewire.org -p 2220`. Use diff to show the password. `diff passwords.new passwords.old`. Make sure to select the entry corresponding to `passwords.new`.
 
### Flag
kfBf3eYk5BPBRzwjqutbbfE887SVc5Yd XXX
