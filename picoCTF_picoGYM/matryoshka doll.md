if we were to use strings on the given file we can see xml code inside of it, 
```
strings dolls.jpg  
```
for that reason i used binwalk to extract another file from inside, based on the name of the exercise we can figure it out we have to do it multiple times, after 4 iterations we get the flag
```
binwalk -e dolls.jpg
```
picoCTF{e3f378fe6c1ea7f6bc5ac2c3d6801c1f}

