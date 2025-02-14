# Finding All the records
<b> 
1. Working through some of the link information, how many columns are in the database?<br />
2. How many records in the database? <br />
3. How many tables are there in the database? </b>
<br /><br />

## How many columns are in the database?
The categories, list products page has 11 columns. The artists one has 4 columns. <br />
All was taken by querying ORDER BY <br /><br />


## How many records in the database? <br />
For all the records, I did this last. I did this after the tables. Changed the
```
http://testphp.vulnweb.com/listproducts.php?cat=1%20UNION%20SELECT%201,2,3,4,5,6,table_name,8,9,10,11%20from%20information_schema.tables%20where%20table_schema=%27acuart%27
```
switched it with 
```
information_schema.columns, and then column_name
```
so it will display every column rather than I go to each tables.<br />
<b>Resulted in 30 data.</b>  I can use “AND table_name =”   function to specify which table they belong to but I didn’t want to that anymore. <br />

![image](https://github.com/user-attachments/assets/20b91d2b-4ad9-4fd3-bb3f-88b8acf08344)![image](https://github.com/user-attachments/assets/5fe72519-a8a2-4c99-b280-ea0b0160f17c)![image](https://github.com/user-attachments/assets/34d1e2d1-36a1-4cc3-90a6-11dc9c539be7)![image](https://github.com/user-attachments/assets/03b8a9ec-359e-4b60-95c6-a338cb0529ff) <br /><br />

## How many tables are there in the database? </b>
There are 8 tables. <br />
Can also use it by replacing some 2, 7 ,9 numbers with table_name and add FROM information_schema.tables WHERE table_schema=”acuart” 
added all the tables contents. For mine, I replaced the 7 so it’s easier to see. <br />
Namely:
<ul>
  <li>artists</li>
  <li>carts</li>
  <li>categ</li> 
  <li>featured</li>
  <li>guestbook</li>
  <li>pictures</li>
  <li>products</li>
  <li>users</li>
</ul>


![image](https://github.com/user-attachments/assets/7f021dcf-85e2-4eaa-8274-e93308f29225)

```
http://testphp.vulnweb.com/listproducts.php?cat=1%20UNION%20SELECT%201,2,3,4,5,6,table_name,8,9,10,11%20from%20information_schema.tables%20where%20table_schema=%27acuart%27
```

<br />

# Conclusions
This marks the end of this lab. <br />
SQL is medium level, if you are diligent and have spare time to actually look through understanding why such injections worked, <br />
the exploitation can get easier. I am someone who do not have experience at all when it comes to these but I was able to do my work. <br />
There are alternative ways to do these, I actually did not follow certain instructions because I thought the instruction was a bit time consuming <br />
(ex. displayed all the records at once, instead of doing it table by table).<br />

In conclusion, having an unsecured website and bad coding can lead to various risks that can be exploited as "easy" as these. <br />
This is also a great way to test your websites against SQL injections, so make sure all security measure in place are working well and sites are programmed neatly.<br /><br />



>[!Important]
>Thank you looking through these! These gave me a headache but fun nonetheless :)
