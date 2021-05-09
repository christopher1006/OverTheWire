# Bandit 11

## Problem Information 
  > The password for the next level is stored in the file data.txt, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions

## Solution
 `ls -Al` reveals the `data.txt` file is already in the home directory. `cat data.txt` returns "Gur cnffjbeq vf 5Gr8L4qetPEsPk8htqjhRK8XSP6x2RHh". In order to remove the Rot13 encoding, run `cat data.txt | tr ‘n-za-mN-ZA-M’ ‘a-zA-Z’`  
### Flag
5Te8Y4drgCRfCx8ugdwuEX8KFC6k2EUu