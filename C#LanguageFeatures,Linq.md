# C# LANGUAGE FEATURES

### IMPLICIT TYPE LOCAL VARIABLE

- variant keyword -> var 

- var -> typecast to  datatype based on value assigned to variable. 
```cs
var a = 10; 
var s = "Hello";
var obj = new DelegateDemo();
```
- only for local variable 
- cannot be used as method paramater
- multiple variable not supported 
```cs
var a,b,c; ❌
```
- value have to assigned while declaring
- null value cannot be used

### NULLABLE TYPE 

1.  Reference type 
     - class
     - string
     - interface
     - object
     - delegate
2.  value type
     - int
     - float
     - double
     - byte
     

- nullable types can be assigned to value type

- null values can be assignes to reference type not cannot be assigned to value , nullable type is used to assign null values to value type

```cs
int? i = null;
public int? property {get; set;}
```

- Gives two properties HasValue (returns boolean)and Value

- HasValue -> checks if it has value
```cs
if(i.HasValue){

}else{

}
```

### EXTENSION METHOD

- we can create out own methods and add to data type.

- Rules 
1. method and class should be static
2. method has to atleast take one parameter
```cs
//eg: create method to check whether number is even or not
static class myext
{
    public static bool IsEven(this int a){// this int implies that the method should be added to int data type
     
       return i%2 == 0;

    }
}

```
### INLINE WARNING
- using inline warning feature we can disable the warning messages

- inline warnings -> naming convention warnings
```cs
#pragma warning disable

#pragma warning restore
```
- to collapse few commented lines
```cs
#region //delegate demo
//
//
//
#endregion
```

### OBJECT INTIALIZER

```cs
Product p = new Product(){pid = 100,pname = "Shirts"};
```

- collection intializer
```cs
List<Product> li = new List<Product>(){
    new Product(){pid = 100,pname="Shirts"};
}
```