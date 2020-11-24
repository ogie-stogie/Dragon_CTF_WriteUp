# Dragon_CTF_WriteUp
### Team: 466 Crew
Taylor Bart<br>
Kamal Nadesan<br>
Matt Evans<br>
John Tiffany<br>
[Dragon CTF Write Up](https://github.com/tbart27/Dragon_CTF_WriteUp)

As a team we were not able to get a flag in this CTF. I focused on the web challenges mostly.
### Web: Harmony
You are greeted with a cool purple terminal where it asks for you login. I was able to create a user and log in then while logged in I was able to create some channels. The whole time I was monitoring what files were being used and I quickly saw that chat.js had the methods I was looking for in the site. After reading through the 600 lines, I wasn't able to see any weaknesses that I could exploit and I still had no idea where to find the flag file itself.
### Web: Scratchpad
In the second web challenge that I found, I believe I was able to identify an XSS vulnerability in the page where you add new notes. I believe the XSS attack can happen due to the content being cut off where I was expecting an injection to cut off:<br>
<br>
![](https://github.com/tbart27/Dragon_CTF_WriteUp/blob/main/web1.PNG)<br>
<br>
You can see that only "> was being shown. However, the site had protection against in-line javascript execution:<br>
<br>
![](https://github.com/tbart27/Dragon_CTF_WriteUp/blob/main/web2.PNG)<br>
<br>
At this point I started looking into how I could potentially change the meta data of the request page to allow in-line execution via either proxy or in the injection itself. However, after no new leads I then tried seeing if the security would handle the login being injected into the note itself:<br>
<br>
![](https://github.com/tbart27/Dragon_CTF_WriteUp/blob/main/web3.PNG)<br>
<br>
I spent the remaining time testing various admin auth attacks via the nested injection.<br>
### Conclusion
This was a more challenging CTF that we all struggled on but I am excited to see if there will be a write up for the web challenges. I was able to read a couple from affinity ctf last week, and was able to see that I missed the mark on a lot of the hints.
