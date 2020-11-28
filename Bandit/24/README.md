# Bandit 24

## Problem Information 
  > A daemon is listening on port 30002 and will give you the password for bandit25 if given the password for bandit24 and a secret numeric 4-digit pincode. There is no way to retrieve the pincode except by going through all of the 10000 combinations, called brute-forcing.

## Solution
> I need to use `telnet` in order to talk to this daemon. To get the IP address, use `hostname -i` and the port number is already given.

`telent 192.168.101.80 30002`
The response tells the user how the bandit24 password as well as the guess need to be on the same line for each and every submission. We now have everything needed in order to attack this password with brute force. Just to make sure I wasn't about to kick down an unlocked door, I tried 0000 at this point.

`#!/bin/bash

Loop through every 4-digit combo starting with 1000 all the way to 9999.
 
### Flag
