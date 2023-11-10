lets first analyze the code : 
``` python 
import string
LOWERCASE_OFFSET = ord("a") # 97

ALPHABET = string.ascii_lowercase[:16] # first 16 characters of alphabet

def b16_encode(plain):
    enc = ""
    for c in plain:
        binary = "{0:08b}".format(ord(c)) #binary format of character's ascii number
        enc += ALPHABET[int(binary[:4], 2)] # first 4 bits says index of alphabet char
        enc += ALPHABET[int(binary[4:], 2)]# last 4 bits says index of alphabet char
    return enc
    
def shift(c, k):
    t1 = ord(c) - LOWERCASE_OFFSET #index of charcter in alphabet 
    t2 = ord(k) - LOWERCASE_OFFSET #index of charcter in alphabet  
    return ALPHABET[(t1 + t2) % len(ALPHABET)]

flag = "redacted"
key = "redacted"
assert all([k in ALPHABET for k in key]) # key has the same domain
assert len(key) == 1 # length of the key is equals to 1 so the key must be one char of the alphabet 

b16 = b16_encode(flag)
enc = ""
for i, c in enumerate(b16):
    enc += shift(c, key[i % len(key)]) # key is constant c is the character of b16 decoded string
print(enc)
```
i wrote the decoder, the most important part is b16_decoder :  
``` python 
import string  
LOWERCASE_OFFSET = ord("a")  
ALPHABET = string.ascii_lowercase[:16]  
encrypted_flag = "mlnklfnknljflfmhjimkmhjhmljhjomhmmjkjpmmjmjkjpjojgjmjpjojojnjojmmkmlmijimhjmmj"  
  
def b16_decode(text):  
   dec_b16 = ""  
   for x in range(0,len(text),2):  
      binary = "{0:04b}".format(ALPHABET.index(text[x]))+"{0:04b}".format(ALPHABET.index(text[x+1]))  
      dec_b16 += chr(int(binary, 2))  
   return dec_b16  
  
def shift(c, k):  
   t1 = ord(c) - LOWERCASE_OFFSET  
   t2 = ord(k) - LOWERCASE_OFFSET  
   return ALPHABET[(t1 + t2) % len(ALPHABET)]  
  
  
for x in ALPHABET:  
   decrypted = ""  
   for i in encrypted_flag:  
      decrypted += shift(i, x)  
   print(b16_decode(decrypted))
```
now we get 16 possible outcome but only one of the results seems like possible flag : 
```
ËÚµÚÛµÇÊÇËÇÌÌÊËÈÇÉ
ÜëÆëì¦ÆØ©ÛØ¨Ü¨¯ØÝ« Ý­« ¯§­ ¯¯®¯­ÛÜÙ©Ø­Ú
íü×üý·×éºìé¹í¹°éî¼±î¾¼±°¸¾±°°¿°¾ìíêºé¾ë
ÈèúËýúÊþÊÁúÿÍÂÿÏÍÂÁÉÏÂÁÁÀÁÏýþûËúÏü
ùÙùÜÛÛÒ ÞÓ ÐÞÓÒÚÐÓÒÒÑÒÐÜÐ
/
/ ê
íììãïäáïäãëáäããâãáíá
!001û-þ -ý!ýô-"ðõ"òðõôüòõôôóôò !.þ-ò/
12?>0
CR=RS=OBOCODDBC@OA
TcNcd.NP!SP T 'PU#(U%#('/%(''&'%STQ!P%R
et_tu?_a2da1e18af49f649806988786deb2a6c # here is the flag !
v`@`rCurBvBIrwEJwGEJIAGJIIHIGuvsCrGt
qQqTSSZV[XV[ZRX[ZZYZXTX
§§¨beddkgliglkcilkkjkiei
©¸¸¹s¥v¨¥u©u|¥ªx}ªzx}|tz}||{|z¨©¦v¥z§
ºÉ¤ÉÊ¤¶¹¶º¶»»¹º·¶¸

```