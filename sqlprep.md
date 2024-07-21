# TRANSACTIONS

- Transactions are a set of one or more database operations that must be completed as a single unit.

- it provides integrity and consistency to data.


## ACID PROPERTIES

1. Atomicity : all operations in a transaction must either complete successfully or fail entirely.

2. Consistency : The data must remain valid and consistent before and after the transaction.
Eg: if the quantity is reduced by 2 in stock table then it shoud be accounted in the orders table

3. Isolation : Concurrent transactions must be isolated from each other. One transaction must not effect the other .

4. Durability : Once a transaction is commited it then the changes made should be permanent even in case of system failure


- Transactions are performed using TCL(Transaction Control Languages) Commands : Begin Commit Rollback

```sql
BEGIN TRANSACTION;

-- SQL statements here (e.g., INSERT, UPDATE, DELETE)

-- If everything is successful, commit the transaction
COMMIT TRANSACTION;

-- If there's an issue, rollback the transaction
ROLLBACK TRANSACTION;


```



- Tansactions can also be used in exception handling 


- Try and catch
```sql
Create Procedure spActorChangeOfTitle
  @name nvarchar(20) , @id int
As
Begin
Begin Try
Begin Transaction
Update Actors  Set FirstName = @name 
Where ActorID=@id;
commit transaction 
End try
Begin catch
  rollback
end catch
end
```


- Transactions can also be used in triggers

```sql
alter trigger tr_insertionprice
on orders
for update
as
begin 
if (select price from deleted) < 100
begin
print 'Cannot update price less than 100'
rollback
end
end
```

