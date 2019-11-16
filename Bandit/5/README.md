# Problem Name

## Problem Information 
  > The password for the next level is stored in a file somewhere under the inhere directory and has all of the following properties:
  
       human-readable
       1033 bytes in size
       not executable

## Solution
 `cd inhere/` and `find -size 1033c -readable` which will return the file location for you to `cat maybehere07/.file2`. The key is to specify no file names and not search for an executable and specify the size limit. While there are plenty of readable files, only one is 1033 bytes. There isn't even an executable of the same size.
 
### Flag
DXjZPULLxYr17uwoI01bNLQbtFemEgo7
