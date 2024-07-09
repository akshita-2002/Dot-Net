# GENERICS

- Collection of related elements(objects)

#### DRAWBACKS OF ARRAY
- size is fixed
- dynamic insertion and deletion not possible
- does not support sorting and filtering(inbuilt function not available)
- does not supports LIFO and FIFO storage



#### GENERICS 
- size is not fixed
- dynamic insertion supported
- sorting inbuilt function available
- LIFO and FIFO 


- import class to use generics
```cs
System.collections.generics
```
Contains classes
1. List
2. Dictionary
3. SortedList
4. Stack
5. Queue
6. Custom class/methods

#### LIST
```cs
List<DataType> l1 = new List<dataType>();
l1.Add(10); //appends at last
l1.Insert(2,43); // to insert dynamically  at position 2


l1.Remove(43); // removes a particular element 
l1.RemoveAll(x=> x==43); // to remove all 43 elements
l1.RemoveAt(2); //remove at a index
l1.RemoveRange(2,5); //Range of index 
l1.RemoveAll(); //removes all values
List<DataType> l2 = new List<dataType>(){10,20,30};

//print
Console.WriteLine(l1[0]);

//length
Console.WriteLine(ob.Count); //count is a property

//how to sort data
l2.Sort();

l2.Reverse(); //to sort in descending order


Console.WriteLine(li.Capacity); //allocates memory beforehand
// for zero -> 0
//for one -> 4 (allocates memory for four elements)
// then doubles -> 8
// then 16
li.TrimExcess(); // to remove the unused memory
```




- Custom Class -> to store more than one datatype
```cs
public class Products
{
    public int ProductId { get; set; }
    public string ProName { get; set; }
}

//method
public void demo2()
{
    List<Products> li = new List<Products>();

    Products p1 = new Products();
    p1.ProductId = 1;
    p1.ProName = "Shoes";

    li.Add(p1);

    foreach (var p in li)
    {
        Console.WriteLine(p.ProductId);
    }

    //to print only product 1
    Products reult = li[0];
    Console.WriteLine(reult.ProductId+" "+reult.ProName);

    //Collection intializer method
    List<Products> l1 = new List<Products>(){
        new Products(){ProductId=1,ProName="Shoes"},
        new Products(){ProductId=2,ProName="Shirt"}
    }
}

```

- List class is similar to array , where in items are accessed using index position 

#### DICTIONARY
 
- items are access using key instead of index position 

```cs
Dictionary<int,string> d = new Dictionary<int,string>();
d.Add(100,"India");
d.Add(200,"Canada");

Console.WriteLine(d[200]);
SortedList<int,string> s = new SortedList<int,string>(d); // to sort acc to key 
foreach(var item in s){
    Console.WriteLine(item.Key+" :"+item.value);
}
```


#### STACK
- LIFO - last items are shown first
- Real Time Examples
1. Browser History

```cs
Stack<string> s = new Stack<string>();
s.push("http://facebook.com");
s.push("http://google.com");
s.push("http://youtube.com");

foreach(var item in s){
    COnsole.WriteLine(item);
}

Console.WriteLine(s.Count);
Console.WriteLine(s.Pop()); //prints and remove the top element
Console.WriteLine(s.Peek()); //prints the top element
```


#### QUEUE

- items are arranged in FIFO ( first in first out)
- Real Time example
1. Bank token 
2. Reservation
