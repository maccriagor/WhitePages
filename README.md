# Challenge Name: WhitePages
**Category:** Forensics  
**Platform:** picoCTF 2019  
**Points:** no info.

## Description
I stopped using YellowPages and moved onto WhitePages... but the page they gave me is all blank!
Link to WhitePages .txt file : https://challenge-files.picoctf.net/c_fickle_tempest/ab5453de03105a8aab9c68b0b46e66a4fe0a781c3915ab519f7fab31b3ce6894/whitepages.txt
## Challenge Hints
There is data encoded somewhere... there might be an online decoder.
## Analysis
- The challenge gives you a "blank page" that seemingly contains nothing but when you use cat to see its content, it shows that there are several empty lines.
- If you open the .txt file and try to select everything inside, theres still nothing to be shown.
- I got the solution for this challenge when searching "blank page ctf" to see if there are similar results because i dont know which "online decoder" is even hinted at from the challenge since my mind was thinking a decoder here must be specialized for blank page or something like that.
- Prop to Almond Force for his solution to a challenge on ctflearn that is similar to the one on picoCTF : https://www.youtube.com/watch?v=G2Te73TA7H0.
## Solution
Step-by-step explanation:

Download the following tool for hex editing : https://mh-nexus.de/en/hxd/

Visit CyberChef to decode the message : https://gchq.github.io/CyberChef/

1. Open the .txt file on hex editor (HxD).
2. While the decode text session on hex editor shows a bunch of gibberish , there are only 3 "letters" being repeated which is "f","a","e" alongside blank spaces. On the offset side, you will see these 4 strings being repeated : e2,80.83 and 20.

* This setting help the RX-SSTV to listen to your .wav file so it can decode the image, remember to switch the device sound output back after finishing with decoding.
  
3. Play each of the .wav files ( you only really need to play the clue files, the transmission file doesnt how any meaningful clue for RX-SSTV decoding progress unless you are on m00nwalk 1 ).
   
* So i was solving this in my college library and i realized that in a loud area, the RX-SSTV ( despite being on audio cable ) would make the would-be-correct decoded image quite blurry. ( This should be what the Clue 2 image mean )

4. Clue 1 should give you a password ( hidden_stegosaurus ) and Clue 3 would give you the following text "ALan Eliasen the future boy" which if you google it, click the first link and you will see a list of tools, pick steganography.

* Before we move to the fifth step, reminder to pick decode mode when you are on future boy site. ( Dont be like me and get stuck for 30 minutes because i didnt realize i was on encode mode )

5. Choose the Transmission .wav file and enter the password given in Clue 1 ( hidden_stegosaurus ) , pick View raw output as MIME-type (text/plain).
## Result
The flag for this challenge is picoCTF{not_all_spaces_are_created_equal_bbc4f54c75763bd78dc840f05eb7a752}. 
