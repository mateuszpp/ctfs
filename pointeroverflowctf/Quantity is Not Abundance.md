## Exercise 
That flag is in an internal location on this site, under /.secret/flag.txt
Once you know where it is, manipulate the site's function to get it!

## Solution
When i opened the website i started with finding the path to the file, quickly you can see that we not have permisson for the flag.txt file.


I went ahead to check out the headers and cookies. After playing the game of tic tac toe we can see the cookie without name and value : "Despite My Best Efforts To The Contrary... It Turns Out I've Won."

Ive decided to put that cookie in the body of get request asking for the flag.txt file. I used burpsuite for that.

## FLAG 

poctf{uwsp_1_h4v3_70_1n5157}
