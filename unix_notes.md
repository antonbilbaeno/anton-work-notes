#bash notes

##Find & replace in directory  
find . -type f -exec sed -i 's/oldtext/newtext/g' {} +  

##Grep before and after line found
e.g. python script.py | grep -A 10 -B 10 "text to look for"  
will print out 10 lines before and after the line where grep finds text

##Symbolic linking
ln -s fileToLink placeToLinkTo  
e.g. ln -s /home/anton/proj/inteliot/src/.libs/libiotgtwy.so.0.0.0 /usr/local/share  

##Checking open ports
netstat -l  
netstat -lp  
netstat -lpn  

##Renewing DHCP?
dhclient -r  
sudo dhclient  

##Untar-ing a .tar.bz2 file
Open a terminal and type:  
tar xvjf filename.tar.bz2  
Which will untar it to the current directory. Normally (99% of the time) it will create it's own subdirectory so you don't need to worry about that.  
Just so you know:  
tar - Tape ARchiver  
And the options:  
x - extract  
v - verbose output (lists all files as they are extracted)  
j - deal with bzipped file  
f - read from a file, rather than a tape device  
"tar --help" will give you more options and info  

