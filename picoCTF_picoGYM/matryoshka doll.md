if we were to use strings on the given file we can see xml code inside of it, 
```
strings dolls.jpg  
```
for that reason i used binwalk to extract another file from inside, based on the name of the exercise we can figure it out we have to do it multiple times, after 4 iterations we get the flag
```
binwalk -e dolls.jpg
```
p�i�c�o�C�T�F�{�e�3�f�3�7�8�f�e�6�c�1�e�a�7f6bc5ac2c3d6801c1f}

