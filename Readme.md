# JAVA DESIGN PATTERNS

A design patterns are well-proved Industry Standand Robust solution for solving the specific problem/task. let us see where we use design patterns with a problem statement. 

### Problem Given:

  <span style="color:#F08080">Suppose you have some database which accept only one thread for CRUD Operations which means you want to create a program for which only a database connection single instance (or object) should be created and that single object can be used by all other classes.</span>

### Solution:

  <span style="color:blue">Singleton design pattern is the best solution of above specific problem.</span>

 Cool Right ! So, every design pattern has some specification or set of rules for solving the problems.

----
### content 

1. [Creational Design Pattern ](/Design-Patterns-Hello-World-Samples/01-Creational-Design-Patterns/)

    * [Singleton Design Pattern ](#singleton)

    * [Factory Design Pattern / Factory Method Design Pattern ](/Design-Patterns-Hello-World-Samples/01-Creational-Design-Patterns/02-Factory-Pattern/)

    * [Abstract Factory Design Pattern](/Design-Patterns-Hello-World-Samples/01-Creational-Design-Patterns/03-Abstract-Factory-Pattern/)

    * [Builder Pattern](/Design-Patterns-Hello-World-Samples/01-Creational-Design-Patterns/04-Builder-Pattern/)

    * [Prototype Pattern](/Design-Patterns-Hello-World-Samples/01-Creational-Design-Patterns/05-Prototype-Pattern/)

2. [Structural Design Pattern](/Design-Patterns-Hello-World-Samples/02-Structural-Design-Patterns/)

----

<a name="singleton"/>

# Singleton Design Pattern 

Singleton pattern *`restricts the instantiation of a class and ensures that only one instance of the class exists`* in the Java virtual machine. 

![singleton](https://user-images.githubusercontent.com/24265936/164861875-3ade0ead-17b8-4eac-bdfe-143ddadd3404.png)


## <b>Real-World Analogy</b>

The government is an excellent example of the Singleton pattern. A country can have only one official government. Regardless of the personal identities of the individuals who form governments, the title, “The Government of X”, is a global point of access that identifies the group of people in charge.

## 😢 Problem

The Singleton pattern solves two problems at the same time, violating the Single Responsibility Principle:

    Ensure that a class has just a single instance

Why would anyone want to control how many instances a class has? The most common reason for this is to control access to some shared resource—for example, a database or a file.

Here’s how it works: imagine that you created an object, but after a while decided to create a new one. Instead of receiving a fresh object, you’ll get the one you already created.

Note that this behavior is impossible to implement with a regular constructor since a constructor call must always return a new object by design.

    Provide a global access point to that instance.

Remember those global variables that you (all right, me) used to store some essential objects? While they’re very handy, they’re also very unsafe since any code can potentially overwrite the contents of those variables and crash the app.

Just like a global variable, the Singleton pattern lets you access some object from anywhere in the program. However, it also protects that instance from being overwritten by other code.

There’s another side to this problem: you don’t want the code that solves problem #1 to be scattered all over your program. It’s much better to have it within one class, especially if the rest of your code already depends on it.


<img width="704" alt="image" src="https://user-images.githubusercontent.com/24265936/164951400-430b817a-d5fb-4824-8b9d-719d96de5cc1.png">


## <b>< / > Pseudocode</b>

### <b>Step 1</b>

Create a Singleton Class. <i style="color:blue">SingleObject.java</i>

```java
public class SingleObject {

   //create an object of SingleObject
   private static SingleObject instance = new SingleObject();

   //make the constructor private so that this class cannot be
   //instantiated
   private SingleObject(){}

   //Get the only object available
   public static SingleObject getInstance(){
      return instance;
   }

   public void showMessage(){
      System.out.println("Hello World!");
   }
}
```

### <b>Step 2</b>

Get the only object from the singleton class. <i style="color:blue"> SingletonPatternDemo.java </i>

```java
public class SingletonPatternDemo {
   public static void main(String[] args) {

      //illegal construct
      //Compile Time Error: The constructor SingleObject() is not visible
      //SingleObject object = new SingleObject();

      //Get the only object available
      SingleObject object = SingleObject.getInstance();

      //show the message
      object.showMessage();
   }
}
```

### <b>Step 2</b>
Verify the output.

```java
Hello World!
```


