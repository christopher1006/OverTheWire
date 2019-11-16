# Bandit 18

## Problem Information 
  > The password for the next level is stored in a file readme in the homedirectory. Unfortunately, someone has modified .bashrc to log you out when you log in with SSH.

## Solution
 Since ssh connections to the shell are being closed on login, the pseudo shell must be forced open with `-t`. If this had not worked, `-T` would have worked by disabling `.bashrc`. In this case, however `ssh -t bandit18@bandit.labs.overthewire.org -p 2220 /bin/sh` works. Note that you must provide directions to a shell or you will still get booted off. Once on, `cat readme` to get the password. 

### Flag
IueksS7Ubh8G3DCwVzrTd8rAVOwq3M5x
