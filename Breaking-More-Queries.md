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

I went to the home index page and then pasted the followings:
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
![image](https://github.com/user-attachments/assets/99b1352a-4aa2-435f-8916-a560904de730)



