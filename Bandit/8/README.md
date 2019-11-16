# Bandit 8

## Problem Information 
  > The password for the next level is stored in the file data.txt and is the only line of text that occurs only once

## Solution
`ls -Al` reveals the `data.txt` file in question for this problem is already present in the home directory. To find the password, sort the data and then pipe to uniq. The reason being that uniq checks only immediately around each line by default so sorting will let it work optimally. `sort data.txt | uniq -u`

### Flag
UsvVyFSfZZWbi6wgC7dAFyFuR6jQQUhR
