# Bandit 1

## Problem Information 
  > The password for the next level is stored in a file called - located in the home directory

## Solution
 `cat /home/bandit1/-` or a bash redirection must be used. This is due to `-` being a synonym to stdin for many programs, if not the operating system itself. By explicitly defining a file, this quirk is bypassed and treated as a file.
 ### Flag
CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9
