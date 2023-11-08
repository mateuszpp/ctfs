what we get is a file that cannot be opened 
the first thing i do is start strings for any interesting data, but dont get any 
so i used xxd to check what is inside, on the begging we can see "BM" telling me
that it is a bit map
when i change the format of the file it still doesnt open 
downloaded some bmp sample file and compared those 2 headers
my file had unusual "BAD0" twice suggesting there is made mistake in a file 
i switched it according to example into 8A 00 and 7C 00 

we actually get a good file now with a message notaflag{sorry}
have in mind a title of the exercise and seeing the unusual format of the photo 
i started manipulating the height of the photo (bear in mind it is in little endian)
we finally get a flag : 
picoCTF{qu1t3_a_v13w_2020}
