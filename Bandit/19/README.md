# Bandit 19

## Problem Information 
  > To gain access to the next level, you should use the setuid binary in the homedirectory. Execute it without arguments to find out how to use it. The password for this level can be found in the usual place (/etc/bandit_pass), after you have used the setuid binary.

## Solution
 `ls -Al` to verify the file in question is available. Note that while the user owner is bandit20, bandit19 is the group owner. This means that I can execute the file but it runs with bandit20 permissions. Note that the file name is red to indicate a heightened permissions situation. This executable simply sends whatever shell command you want to be executed as bandit20, so `./bandit20-do cat /etc/bandit_pass/bandit20` will output the password that bandit19 would normally never have access to.
 
 ### Flag
GbKksEFF4yrVs6il55v6gwY5aVje5f0j
