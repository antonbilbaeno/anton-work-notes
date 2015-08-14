#bash notes

##Find & replace in directory  
find . -type f -exec sed -i 's/oldtext/newtext/g' {} +  

##Symbolic linking
ln -s fileToLink placeToLinkTo  
e.g. ln -s /home/anton/proj/inteliot/src/.libs/libiotgtwy.so.0.0.0 /usr/local/share  
