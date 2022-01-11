


# **OOO principles**

## **principles**
```
1. SRP -> Single Responsibility Principle
2. OCP -> Open Close Principle
3. ISP -> Interface Segregation
4. DIP -> Dependency Inversion Principle
5. LSP -> Liskov Substitution Prinicple

--> SOLID Principles
```

### **SRP** - single responsability principle
- **one responsablitiy**: Have one, and only one, reason to change. when multiple responsibilities -> split class

#### ***example***
This is not good because the Cardgame class has too many responsablities.

![](/images/srp1.png "srp1")

A better solution would be :

![](/images/srp2.png)
 ___


### **OCP** - Open Close Principle
- **open** for extension, but **closes** for modification
- New functionality should be added with minimum changes in the existing code

#### ***example***
 Here you can see that for every new time of employee there will be need to write all the code, in which you can set the common details in one class, and the specificate in an other.

 ![](/images/ocp1.png)

 A better solution would be to put the common details in the employee class.

 ![](/images/ocp2.png)
___

### **ISP** - Interface Segregation
- Clients should not be forced to depend upon interfaces that they don't use. 
- interfaces should be cohesive:
1. small and specifix
2.if multiple responsibilities -> split interface

![](/images/isp1.png)
![](/images/isp2.png)
___
### **DIP** - Dependency Inversion Principle
- High level modules should not depend on low-level modules. Both should depend on abstraction.
- Abstraction should not depend on details. Details should depend on abstractions.

![](/images/dip1.png)
![](/images/dip2.png)

### **DIP** - Dependency Inversion Principle
- If a program module is using the reference of a Base class, then it should be able to replace the Base class with a Derived class without affecting the functioning of the program module.
- Everywhere you use an instance of a Base class, you should be able to replace that instance with an instance of a sub class.
- Sub classes are allowed to do MORE than a super class, but NOT LESS
___


## **Patterns**
```
1. Strategy
2. State
3. Observer
4. Singleton
5. Enumerations
6. Simple Factory 
7. Reflection
8. Facade
9. Adaptor
10. Template method
11. Decorator
```
___
### **Strategy**
**Why?**
```
Define family of algorithms

Encapsulate each algorithm

which makes them interchangeable
```
Ensures the code is :

1. flexible= choose a different algorithm @runtime.
2. extendable: add a new algorithm without modifying existing code.

**How?**
```
create interface for algorithm.

create implementing classes for algorithms.

method in context class uses the interface to execute the algorithm, instead of doing it itself.
```
[video hierover + voorbeeld](https://www.youtube.com/watch?v=Nrwj3gZiuJU)

SOLID?
````
SRP? 

    OK for the ConcreteStrategy classes: each sstratagy)class has 1 responsablilty: execute the algorithm it encapsulates.

    
    Pay attention: also check the rest of your design

OCP?

    Almost ok!

    Add new strategy, minimal rework in your client class
````

___

### **State**

**Why?**
````
Change behavior when state changes

Avoid code that is hard to maintain (ifs)

Easy to extend
````

**How?**
````
Create interface for state

Create implementing classes for states

Context class contains all possible states

Context class knows its current state

Method in context class uses the current state to handle the request, instead of doing it itself
````

**State vs. Strategy**
````
State                                       Strategy
Client does not chooese, depends            Client chooses strategy
on the context

Alternative for ifs                         Alternative for subclassing
````

[video hierover + voorbeeld](https://www.youtube.com/watch?v=abX4xzaAsoc)

SOLID?
````
SRP
    OK. Each state is encapsulated in its own class.

OCP 
    NOK: introducing a new state means modifying
        the context class
        (at least some of) the other states

DIP
    OK: state interface

Liskov
    Not applicable
````
___
