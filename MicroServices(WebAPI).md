# MICROSERVICES

- service -> set of actions

- microservices -> divide the service (project) into smaller parts ( each part is part of project)

### MONOLITHIC APPLICATION

![alt text](image-94.png)

- persistent layer -> database  (Model,context pages)
- presentation layer -> UI
- service layer -> backend (Controller)

- if application is not micro services then it is monolothic 

![alt text](image-93.png)


- single deployment -> to make the application online

- single runtime -> single language is used 

- single database -> sql server

- interaction between classes is most often synchronous

- each layer is separated with packages/libraries 


![alt text](image-95.png)

- single frontend , many controllers and a single database 


- benefits

1. simple to build
2. simple test
3. simple deploy and develop


- Drawbacks

1. start of app will take long time  -> executes all the controllers
2. new team members difficult to understand the project complexity
3. bigger the bigger the team 
4. cannot update with new technology (since single kanguage is allowed)
5. need more CPUs
6. no flexibility ( one layer effects the other)
7. longer development lifecycle
8. maintenance is difficult 
9. fault tolerance brings down entire application



### MICROSERVICES
![alt text](image-96.png)
- 
