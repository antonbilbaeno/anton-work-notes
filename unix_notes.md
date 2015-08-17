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

