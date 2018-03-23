# AngstromCTF2018
Write-Ups
# GIF
I dug into this not ever really attacking a Stego challenge before. The only one's I've done I've gotten stumped and had to move on. I wasn't willing to let this one go.
### Image in question
![alt text](https://github.com/BicNasty/AngstromCTF2018/blob/master/jiggs2.gif)  
The hint on this being that this file was too large. The file size defintely did not line up with what I was looking at.  
  
**1.06 MB for a small GIF that doesn't work?**
  
 I changed the extension to .zip and .rar seeing the size. Nothing. I also tried changing to .PDF and nothing. I also ran this through StegSolve and wasn't able to find anything of note. !! Then, I looked at the hex with HdX and saw some oddness.  
   
 ![alt text](https://github.com/BicNasty/AngstromCTF2018/blob/master/JiggsHex.png)
   
     
Alright, so I noticed that the header is a PNG header. So, let's change the header to PNG. Same image. From there I searched the header for the ending of the .PNG hex which is IEND. Once I found that, I removed that from the IEND to the top of the file and removed it. Ensuring preservation of ‰ text prior to PNG. Once done, the image moved onto the next PNG! Getting closer. After the image changed to a new one, I searched the hex file and there were multiple PNGs in here. Around 7. So, I repeated the above steps over and the image changed again. Eventually, I found this!  

![alt text](https://github.com/BicNasty/AngstromCTF2018/blob/master/JiggsSolved.png)    
  
# FLAG CAPTURED!
