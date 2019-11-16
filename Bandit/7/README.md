# Bandit 7

## Problem Information 
  > The password for the next level is stored in the file data.txt next to the word millionth

## Solution
 `ls -Al` reveals the `data.txt` file is already in the home directory. To find the password beside the word millionth, I found that grepping for the word by itself seemed to be taking an inordinate amount of time. However, a relatively quick return is achieved when sorting it first befire piping to grep. `sort -f data.txt | grep "millionth"`
 
### Flag
cvX2JJa4CFALtqS87jk27qwqGhBM9plV
