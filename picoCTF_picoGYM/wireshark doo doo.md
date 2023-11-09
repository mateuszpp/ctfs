we get a pcapng file with a thousand of packets 
to make it easier to look through data i opened : 
follow tcp stream and saved them into txt files in order to use strings to catch the string with beginning "pico"
to my surprise i didnt get any so i opened wireshark once again, i looked fastly through all of the streams and instantly saw some string in format of flag, however it was obviously encrypted, cvpbPGS{c33xno00_1_f33_h_qrnqorrs}
based on the look it was probably ROT - so i pushed it into decoder indeed it was ROT 13 and got a flag : 
picoCTF{p33kab00_1_s33_u_deadbeef}