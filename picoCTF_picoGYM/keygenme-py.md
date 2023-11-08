we get python code and our job is to figure out a code which is also our flag : 

```python 
import hashlib  
  
key_part_static1_trial = "picoCTF{1n_7h3_|<3y_of_"  
key_part_dynamic1_trial = "xxxxxxxx"  key_part_static2_trial = "}"  
username_trial = b"PRITCHARD"  
tab=[]  
for x in [4,5,3,6,2,7,1,8]:  
    tab.append(hashlib.sha256(username_trial).hexdigest()[x])  
key_part_dynamic1_trial=''.join(tab)  
  
res = key_part_static1_trial+key_part_dynamic1_trial+key_part_static2_trial  
print(res)
```