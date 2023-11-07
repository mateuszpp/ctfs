
## Exercise 

Hey, contestants! Allow me to take this opportunity to debut the hottest new social media platform on the planet. I call it [ManyKins](https://nvstgt.com/ManyKin/index.html)! There is also ZERO chance it has ANY vulnerabilities that might allow one to find the flag (under /secret/flag.pdf)!

## Solution 
When we try path traversal we get a communicat that file couldnt be loaded however it was OK response so i opened burpsuite and sent the request for the file once again using repeater, and we get the flag inside the response body
![[Pasted image 20231105201904.png]]
