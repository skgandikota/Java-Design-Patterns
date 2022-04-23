# Creational Design Patterns

Creational design patterns provide solution to *`instantiate a object`* in the best possible way for specific situations.

 1 [Singleton Design Pattern ](/01-Creational-Design-Patterns/01-Singleton-Pattern/)

2 [Factory Design Pattern / Factory Method Design Pattern ](/01-Creational-Design-Patterns/02-Factory-Pattern/)

3 [Abstract Factory Design Pattern](/01-Creational-Design-Patterns/03-Abstract-Factory-Pattern/)

4 [Builder Pattern](/01-Creational-Design-Patterns/04-Builder-Pattern/)

5 [Prototype Pattern](/01-Creational-Design-Patterns/05-Prototype-Pattern/)


---

 
## 1. Singleton Pattern

Singleton pattern *`restricts the instantiation of a class and ensures that only one instance of the class exists`* in the Java virtual machine. 

![singleton](https://user-images.githubusercontent.com/24265936/164861875-3ade0ead-17b8-4eac-bdfe-143ddadd3404.png)


## 2. Factory Pattern

The factory design pattern is used *`when we have a superclass with multiple sub-classes and based on input, we need to return one of the sub-class`*. This pattern takes out the responsibility of the instantiation of a class from the client program to the factory class. 

![factory](https://user-images.githubusercontent.com/24265936/164863023-1dc99a2f-7214-4714-b34e-45a242ee5d47.png)


## 3. Abstract Factory Pattern

Abstract Factory pattern is similar to Factory pattern and it’s a *`factory of factories`*. If you are familiar with the factory design pattern in java, you will notice that we have a single Factory class that returns the different sub-classes based on the input provided and the factory class uses if-else or switch statements to achieve this.

In Abstract Factory pattern, we get rid of if-else block and have a *`factory class for each sub-class and then an Abstract Factory class that will return the sub-class based on the input factory class`*.

![abstract factory](https://user-images.githubusercontent.com/24265936/164872998-941537d8-fcf9-4ae1-84db-dc64b36798ad.png)

## 4. Builder Pattern

This pattern was introduced to solve some of the problems with Factory and Abstract Factory design patterns when the Object contains a lot of attributes. Builder ```pattern solves the issue with a large number of optional parameters and inconsistent state by providing a way to build the object step-by-step and provide a method that will actually return the final Object```

![builder-design-pattern](https://user-images.githubusercontent.com/24265936/164873287-8c016654-192f-4c7b-875d-13d2beecb275.png)


## 5. Prototype Pattern

The prototype pattern ```is used when the Object creation is a costly affair and requires a lot of time and resources and you have a similar object already existing. So this pattern provides a mechanism to copy the original object to a new object and then modify it according to our needs```. This pattern uses java cloning to copy the object.

![Prototye](https://user-images.githubusercontent.com/24265936/164873394-b7596740-d5df-4259-a204-f0ff8ca7780c.png)