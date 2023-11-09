one part of the flag is in the mycss.css
```
 CSS makes the page look nice, and yes, it also has part of the flag. Here's part 2: h4ts_4_l0 */
```

one part is html 
```
Here's the first part of the flag: picoCTF{t 
```
*  
in js we see there a hint to the flag : 
```
/* How can I keep Google from indexing my website? */
```

after googling i found out about robots.txt : 
```
http://mercury.picoctf.net:44070/robots.txt
```
we get another part : 
```
Part 3: t_0f_pl4c
```

we get yet another hint : 
```
I think this is an apache server... can you Access the next flag?
```
so i look in /htaccess file which manages permissions of  Apache Service 
```
# Part 4: 3s_2_lO0k
# I love making websites on my Mac, I can Store a lot of information there.
```
.DS_store  - DS_Store is a file that **stores custom attributes of its containing folder**, such as folder view options, icon positions, and other visual information. The name is an abbreviation of Desktop Services Store, reflecting its purpose for MACS 
```
Congrats! You completed the scavenger hunt. Part 5: _7a46d25d}
```
flag : 
``` 
picoCTF{th4ts_4_l0t_0f_pl4c3s_2_lO0k_7a46d25d}
```