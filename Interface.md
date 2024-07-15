# INTERFACE

- same as class but no implementation
- has varaibles,methods,properties
![alt text](image-18.png)
- only declaration
- in  C# variables not supported in interface
- implementation is handled using class
- access specifiers cannot be used

![alt text](image-19.png)

- access specifiers are not allowed in interface

- Advantages:

1. Maintains standardization : proper naming conventions, it will force the class to use the signature used in the interface

2. show only the relevant methods.

```cs
Idbinter ob = new InterfaceDemo(); //Idbinter is interface name and InterfaceDemo is class name
// This means we can only use the methods of Idbinter interface
```

3. common method signature
- we can methods with same name and signatures in a class using interface
![alt text](image-20.png)
![alt text](image-21.png)



# DELEGATES 

- function pointers

- is a method without any logic
```cs
public delegate void show();
public void hello()
{
}
show obj = hello
```
- this method can point to another method with same signature
- if delegate is invoked the method is called
- invoke function is inbuilt 
```cs
obj.invoke();
```

- calling this way makes application logic independent

![alt text](image-22.png)

![alt text](image-24.png)

- if parameters needed , invoke must also contain parameters
![alt text](<Screenshot 2024-07-08 154134.png>)

- if only one line of code no need of methods
![alt text](image-25.png)


- even more easier using lambda expression 
![alt text](image-26.png)