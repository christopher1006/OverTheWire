# Bandit 20

## Problem Information 
  > There is a setuid binary in the homedirectory that does the following: it makes a connection to localhost on the port you specify as a commandline argument. It then reads a line of text from the connection and compares it to the password in the previous level (bandit20). If the password is correct, it will transmit the password for the next level (bandit21).

## Solution
 > Set up two SSH sessions on the bandit20 server. One will be running a network daemon and the other will be used to check for that the daemon is working as well as executing the setuid binary. On the first terminal, `echo "GbKksEFF4yrVs6il55v6gwY5aVje5f0j" | nc -l -p 31000` to put the password from bandit19 on a port, ready to be listened to. The port number itself doesn't matter too much, just check it doesn't conflict with an active port via `nmap localhost`. Now switch to your second terminal. To verify that your daemon is working run `nmap localhost -p 31000` and see that your port is listed as open. This will cause the daemon to shut off however so make sure to restart it in your first terminal. To retrieve the password, `./suconnect 31000`. Check back on the first terminal and you will see that the bandit20 password has been sent to your daemon.
 
### Flag
`gE269g2h3mw3pwgrj0Ha9Uoqen1c9DGr`
