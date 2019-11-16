# Bandit 14

## Problem Information 
  > The password for the next level can be retrieved by submitting the password of the current level to port 30000 on localhost.

## Solution
 Connect to the server using the private key instead of the normal type in password `ssh -i sshkey.private bandit14@bandit.labs.overthewire.org -p 2220`. `cat /etc/bandit_pass/bandit14` to ge the password needed to send to local host. Password is `4wcYUJFw0k0XLShlDzztnTBHiqxU3b3e`. Connect to local host with `nc 127.0.0.1 30000` and type the aforementioned password before hitting enter again. The next level password is returned.

### Flag
BfMYroe26WYalil77FoDi9qh59eK5xNr
