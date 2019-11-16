# Bandit 15

## Problem Information 
  > The password for the next level can be retrieved by submitting the password of the current level to port 30001 on localhost using SSL encryption.

## Solution
 After connecting to the server and logging on, use openssl s_client to connect to the local host, thus providing an SSL encrypted connection and satisfying the challenge rules when you submit the same password as you logged on with in the ssh connection. `openssl s_client -connect 127.0.0.1:30001` Paste the password in, press enter, and the next password is revealed.
 
 ### Flag
cluFn7wTiGryunymYOu4RcffSxQluehd
