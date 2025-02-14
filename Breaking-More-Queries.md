# Breaking More Queries
Using ORDER BY keyword to sort the records in ascending or descending order for id=1
```
http://testphp.vulnweb.com/artists.php?artist=1 order by 1
```
<b>What result do you get? How did you modify the link to see other records?</b> <br />
Answered in the first part, I went through the first two links, so I was doing it in that order.<br /><br />


But it showed a 2 on the artist header and a 3 on the descriptions. I tried the other tabs to have an alternative way of finding out the tables. <br />
I tried the commands on the second SQL tutorial link. I tried looking for the “listproducts” but it was not anywhere. <br />

So I copied and pasted some of the sample links form the tutorial but the whole site cannot be reached so I did step slowly as follows.<br />

I went to the home index page and then pasted the following:
```
http://testphp.vulnweb.com/listproducts.php?
```
Which errored, so then, 
```
http://testphp.vulnweb.com/listproducts.php?cat = 1
```

![image](https://github.com/user-attachments/assets/e330819b-fee7-405a-a18c-3164cc04d52c)
Also errored. <br /><br />

So in the title page it says pictures so there’s a database for the pictures somewhere.<br />
so I went back to check around and “listproducts” is under the categories page.<br />
so just navigating around, instead of copy/paste.<br />
```
http://testphp.vulnweb.com/listproducts.php?cat=1
```
Should pop up these contents.
![image](https://github.com/user-attachments/assets/99b1352a-4aa2-435f-8916-a560904de730) <br />

So I then went to to do ORDER BY <br />
1, did nothing, 2 rerranged the contents and so on <br />
![image](https://github.com/user-attachments/assets/8818656e-2553-42bc-98e8-a4917f3f489e)<br />

Stopped at ORDER BY 12, because now there’s an error. So this one has 11 columns only. <br />
![image](https://github.com/user-attachments/assets/b4a6bef6-d924-45ed-9760-d3fb11c60290)<br />

Then used the UNION SELECT<br />
```
http://testphp.vulnweb.com/listproducts.php?cat=1%20UNION%20SELECT%201,2,3,4,5,6,7,8,9,10,11 
```
which added a content with numbers. 2, 7 ,9 are numbers we can modify to for more injections. <br />
![image](https://github.com/user-attachments/assets/8ffb59a0-61ac-43f3-b69b-3011e1b4d28c)<br />

9 was a hyperlink and hovering showed this: artist=10
![image](https://github.com/user-attachments/assets/7eec124c-779f-41a6-98dd-7ffc6789e3b7)

So 10 artists in record?<br />

>[!NOTE]
>Next, finding all the records!

