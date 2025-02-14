# First Injection and Exploring

To start, the lab's first step is to analyze what happens if you tried an injection like this.
```
http://testphp.vulnweb.com/artists.php?artist=1
```
So before I did the injection, I looked over what information is publicly out in the site just so I can tell any differences after injecting. <br />

So then first tried the commands on the second link from my resources.<br />
I added a ‘ <br />

Result: 
![image](https://github.com/user-attachments/assets/ab533ff6-7043-4fb4-9a2e-8a18aee6ef13)

Then I did: 
```
ORDER BY 1.
```
I did notice that the space in the URL translates to %20 but the site just went back to normal. <br />
![image](https://github.com/user-attachments/assets/96dd693d-4e1f-4868-bb68-4db854ee4c30)  <br />


removing the space result to an error again.<br />
![image](https://github.com/user-attachments/assets/c61e8fc5-c1f2-4926-bbbb-0cd2cf0ab335)

