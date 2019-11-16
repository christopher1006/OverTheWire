# Bandit 6

## Problem Information 
  > The password for the next level is stored somewhere on the server and has all of the following properties:

      owned by user bandit7
      owned by group bandit6
      33 bytes in size

## Solution
 `find / -user bandit7 -group bandit6 -size 33c` which will search for all files owned by bandit7. You can manually search it for the one file that doesn't say `Permission denied` or `No such file or directory` but that's for people who aren't lazy. I, being in the latter category, recommend you use `find / -user bandit7 -group bandit6 -size 33c 2>&1 | grep -v "Permission denied" | grep -v "No such file or directory" | xargs cat` as this will filter out all of the error messages and print out the contents of the file that would be left over.
 
 ### Flag
HKBPTKQnIay4Fw76bEy8PVxKEDQRKTzs
