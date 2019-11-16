# Bandit 10

## Problem Information 
  > The password for the next level is stored in the file data.txt, which contains base64 encoded data

## Solution
`ls -Al` reveals the `data.txt` file already in the home directory. `cat data.txt` returns the base64 encode in question. By sending that to base64, you'll find the decoded password. `cat data.txt | base64 -d`

### Flag
IFukwKGsFW8MOq3IRFqrxE1hxTNEbUPR
