# Bandit 16

## Problem Information 
  > The credentials for the next level can be retrieved by submitting the password of the current level to a port on localhost in the range 31000 to 32000. First find out which of these ports have a server listening on them. Then find out which of those speak SSL and which don’t. There is only 1 server that will give the next credentials, the others will simply send back to you whatever you send to it.

## Solution
 `nmap -p31000-32000` Reveals two potential ports. Using `openssl s_client -connect 127.0.0.1:31518` gets certificate authentication. By entering the password, a ssh key is returned for the next level.
### Flag
See file
