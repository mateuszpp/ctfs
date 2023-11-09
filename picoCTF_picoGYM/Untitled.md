sorry_but_this_isn't_it  LOL
![[Pasted image 20231109221717.png]]
funny !
first of all i have read the file via strings, i saw there is a lot of files inside so i used tool 
called binwalk in order to extract all the files, 
```
binwalk -e Foren*
```
then i went through all directories : 
```
ls -alR 
```
there was one file named hidden : 
```
ZmxhZzogcGljb0NURntEMWRfdV9rbjB3X3BwdHNfcl96MXA1fQ
```
i have put it into base64 in UTF8 
and got the flag : 
```
flag: picoCTF{D1d_u_kn0w_ppts_r_z1p5}
```