the algorithm is based on ROT47 but the alphabet is not typical, it is symmetrical function so we need to do it once more on encoded text to get the flag 
```python
alphabet = "!\"#$%&'()*+,-./0123456789:;<=>?@ABCDEFGHIJKLMNOPQRSTUVWXYZ"+ \  
            "[\\]^_`abcdefghijklmnopqrstuvwxyz{|}~"  
bezos_cc_secret = "A:4@r%uL`M-^M0c0AbcM-MFE055a4ce`eN"  
decoded=""  
for c in bezos_cc_secret:  
        index = alphabet.find(c)  
        original_index = (index + 47) % len(alphabet)  
        decoded = decoded + alphabet[original_index]  
print(decoded)
```
