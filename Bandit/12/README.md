# Bandit 12

## Problem Information 
  > The password for the next level is stored in the file data.txt, which is a hexdump of a file that has been repeatedly compressed. For this level it may be useful to create a directory under /tmp in which you can work using mkdir. For example: mkdir /tmp/myname123. Then copy the datafile using cp, and rename it using mv (read the manpages!)

## Solution
 `ls -Al` reveals the `data.txt` file in question. Make a directory in /tmp and copy `data.txt` so it's easier to convert the file back to something readable. `mkdir /tmp/whateverYouWantToCallThis`, `cp data.txt /tmp/whateverYouWantToCallThis`, `cd /tmp/whateverYouWantToCallThis`. 
 
 `cat data.txt` and check the header. You will see 1f8b08, indicating you're looking at a .gz file. `xxd -r data.txt > bin.gz` will make a new file that is binary and can be unzipped with `gunzip bin.gz`. `file bin` to find that you're looking at a bzip2 compression. `bzip -d bin` to decompress. The new file is called `bin.out` so check what it is by typing `file bin.out`. You should see it is a gzip compression. `mv bin.out bin.gz` to make a propper suffix. `gunzip bin.out` to decompress. `file bin` shows it is now a POSIX tar archive. `tar -xvf bin.tar` will result in a file called `data5.bin` which is actually just another tar file according to `file data5.bin`. `mv data5.bin bin.tar` to correct the suffix. `tar -xvf bin.tar` reveals a new file, `data6.bin`. This one is a bzip2 compression. `bzip2 -d data6.bin` which then feeds through file to reveal another tar. `file data6.bin.out`. `mv data6.bin.out data6.tar`. `tar -xvf data6.tar` to decompress the file. This results in `data8.bin`. `file data8.bin` shows it is a gzip. `mv data8.bin data8.gz` to set the correct suffix and `gunzip data8.gz`. `file data8` reveals an ASCII file. `cat data8` reveals the password.
 
 
### Flag
8ZjyCRiBWFYkneahHwxCv3wb2a1ORpYL
