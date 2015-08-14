#cpp notes
##Enabling core dump from segmentation fault
1. check setting  
ulimit -c  
2. set to unlimited  
ulimit -c unlimited  
3. confirm settings applied  
ulimit -c  
*will need to re-enable for each new terminal window

##Investigating core dump
1. Using gdb  
gdb program core  
e.g. gdb ./test/.libs/run_ut core  
2. backtrace  
bt  
3. check threads  
info thread  
4. go to a thread  
thread 3  

