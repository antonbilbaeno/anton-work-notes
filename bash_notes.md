#bash notes

##Find & replace in directory  
find . -type f -exec sed -i 's/oldtext/newtext/g' {} +  

