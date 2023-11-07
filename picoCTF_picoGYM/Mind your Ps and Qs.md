p* q
euler's function - (p-1)(q-1) = y
e < y  
d * e = 1 (mod y)
public key - n,e 
private key - n,d
c- ciphertext
### parameters
c: 62324783949134119159408816513334912534343517300880137691662780895409992760262021
n: 1280678415822214057864524798453297819181910621573945477544758171055968245116423923
e: 65537

## solution
after using factorDB for n we get : 
1899107986527483535344517113948531328331,
674357869540600933870145899564746495319033

this is actually everything we need to get it to the online cracker, i used dcode 
we put in cipher text, "e", "n" and the factorized numbers :"p" and "q"
## flag 
picoCTF{sma11_N_n0_g0od_05012767}
