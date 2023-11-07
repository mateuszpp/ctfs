## description
Who doesn't love cookies? Try to figure out the best one.

## solution
we see the page on which we can write a flag and get a response 
if we check the cookies after writing anything we can the value of the cookie is enumerate just like 1,2,3, etc. 
probably by changing the value of the cookie we will find out the cookie 
for this reason i  created script in python 
```python 
import requests  
  
session = requests.session()  
  
for x in range(28):  
    response = session.get('http://mercury.picoctf.net:xxxxx/check', cookies={'name': str(x)})  
    solution = response.text.find('pico')  
    if solution != -1:  
        print(response.text[solution:response.text.find('}')+1])
```
it prints the response which include "pico" - the flag