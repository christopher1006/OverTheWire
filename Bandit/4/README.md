# Bandit 4

## Problem Information 
  > The password for the next level is stored in the only human-readable file in the inhere directory. Tip: if your terminal is messed up, try the “reset” command.

## Solution
 `ls` will show a set of ten files. Using `file ./*` will return the list of files with their detected data types. file07 turns out to have ASCII text and contains the password. `cat file07` for the answer.
### Flag
koReBOKuIDDepwhWk7jZC0RTdopnAYKh
