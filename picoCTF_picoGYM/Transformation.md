## description
灩捯䍔䙻ㄶ形楴獟楮獴㌴摟潦弸弰㑣〷㘰摽
wonder what this really is... `''.join([chr((ord(flag[i]) << 8) + ord(flag[i + 1])) for i in range(0, len(flag), 2)])`
## solution 
```python 
print(ord("灩")) # unicode of this symbol  28777
x = "灩"  
y= chr((ord("p")<<8)+ord("i"))  
print(x==y) # true  
print(chr((ord("p")<<8)+ord("i"))) 
#i did it to figure out how it work and if im right, first two letters of the flag  "pi" swap into this chinese character

tab = []  
for x in flag:  
    char = ord(x)  
    first_val = char >> 8  
    sec_val = char - (first_val << 8)  
    tab.append(chr(first_val))  
    tab.append(chr(sec_val))  
res = "".join(tab)  
print(res)
# it took me way to long for such an exercise lol ;)
```
picoCTF{16_bits_inst34d_of_8_04c0760d}