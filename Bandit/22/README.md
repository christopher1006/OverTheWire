# Bandit 22

## Problem Information 
  > A program is running automatically at regular intervals from cron, the time-based job scheduler. Look in /etc/cron.d/ for the configuration and see what command is being executed.
  
  > NOTE: Looking at shell scripts written by other people is a very useful skill. The script for this level is intentionally made easy to read. If you are having problems understanding what it does, try executing it to see the debug information it prints.

## Solution
  > After connecting to the server `ls -al /etc/cron.d` to see what cronjobs are available. `cat cronjob_bandit23` to see what the output is. It will point you to `/usr/bin/cronjob_bandit23.sh`. `cat` the file and read through the script. It is a bash script that takes the result of `whoami` and then converts to an md5sum which is the target file name. The goal is to get `myname` to be bandit23 as this will output the password to an accesible temporary file. I can't edit the script and there's no way I know of to change `whoami` but I do not need any of that. It's seems likely the file I'm after has already been made. Either by the original makers of the CTF challenge or just leftover from someone else doing it. So put `echo I am user bandit23 | md5sum | cut -d ' ' -f 1` on the command line. This will give you the correct hash of the target file. From there, just `cat /tmp/8ca319486bfbbc3663ea0fbe81326349` and the password should be returned.
### Flag
`jc1udXuA1tiHqjIsL8yaapX5XIAI6i0n`
