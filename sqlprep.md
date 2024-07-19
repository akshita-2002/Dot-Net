# TRANSACTIONS

- Transactions are a set of one or more database operations that msut be completed as a single unit.

- it provides integrity and consistency to data.


## ACID PROPERTIES

1. Atomicity : all operations in a transaction must either complete successfully or fail entirely.

2. Consistency : The data must remain valid and consistent before and after the transaction.
Eg: if the quantity is reduced by 2 in stock table then it shoud be accounted in the orders table

3. Isolation : Concurrent transactions must be isolated from each other. One transaction must not effect the other .

4. Durability : Once a transaction is commited it must persistent even in case of system failure.


- Transactions are performed using TCL(Transaction Control Languages) Commands : Begin Commit Rollback

- If we start a transaction and doesn't commit it then the transaction will be in loop

```sql
Begin TRANSACTION
Update Actors
Set FirstName = 'Prabhas fun'
Where ActorID = 11
```

- Until the transaction is not committed we can revert the changes using 
```sql
ROLLBACK
```


- Tansactions can also be used in exception handing 


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


- Transsactions can also be used in triggers

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

