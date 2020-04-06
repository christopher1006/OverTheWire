# Bandit 21

## Problem Information 
  > A program is running automatically at regular intervals from cron, the time-based job scheduler. Look in /etc/cron.d/ for the configuration and see what command is being executed.
  
## Solution
  > Once connected to the server, `ls -al /etc/cron.d` and look for `cronjob_bandit22`. The output should tell you that a shell script is being run with the output going to `/dev/null`. Check the shell script with `cat /usr/bin/cronjob_bandit22.sh` and you will see two directories with one outputting to the other. The original file the password is in lies in `/etc/bandit_pass_bandit22`, forbidden lands for us Bandit21 peasantry. However, it outputs to `/tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv` which is a file definitely within our permission set. `cat /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv` and a password you shall receive.
  
### Flag
`Yk7owGAcWjwMVRwrTesJEwB7WVOiILLI`
