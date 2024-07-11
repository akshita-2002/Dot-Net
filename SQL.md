# SERVER TYPE

- Integration Services : for moving data from one server to another (sql,oracle)

- Reporting Services : has option of generating charts,PDFs

- Azure SSIS Integration Runtime : to connect to cloud 

- Database Engine : to store data 


# SERVER NAME 
- to connect with any system databse

# BUILT IN DATABASES
1. master : stores authentication ,credentials , security related database , permisssion of objects.

2. model
```sql
sp_help -- to get all tables,procedures,view
sp_help tablename --to get details of table
sp_rename oldname , newname --to rename table
sp_helpdb  --gives all databases
sp_helpdb slk --it gives information about specific database



EXEC sp_dboption 'sales','offline','TRUE'
```

- two files get created whenever we create a database -mdf files (all the tables created are stored, pysically stores) and ldf files(transaction information)

- when we rollback the information gets restored, it comes from ldf files


- the built in procedures are stored in model database


3. msdb : stores jobs and alerts(notifications)
what alerts , at what time the alert should occur all these are stores. Jobs , the queries are not executed immediately , they are scheduled and executed automatically.

4. tempdb : the tables created are temporary , once the server is restarted , the tables are lost. Sorting (when we sort , to rearrange the rows tempdb is used) and groupby.


- when we create a database -> the intial size is 16MB .
- to create a databse of our own size
![alt text](image-35.png)
FileGrowth -> when the size is full , it increases by 20% 
- the log file should be atleast 30% of database size

- alter the database
![alt text](image-36.png)


