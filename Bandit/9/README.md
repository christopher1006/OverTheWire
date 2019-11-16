# Bandit 9

## Problem Information 
  > The password for the next level is stored in the file data.txt in one of the few human-readable strings, beginning with several ‘=’ characters.

## Solution
 `ls -Al` reveals the `data.txt` file already in the home directory. There's probably a cleaner way to do this but I just used strings to find the human readable portion and piped it to grep with the only standard being it had a few equal signs. You'll get a couple other returns but only one matches the previous passwords. `strings data.txt | grep "===*`

### Flag
truKLdjsbJ5g7yyJ2X2R0o3a5HQJFuLk
