+++
title = "OOPs"
date = 2019-11-27
toc= true
+++

1. Types Of Polymorphism
	 1. Complie Time/Static Polymorphism
		- Achieved by Method Overloading.
		- Function/Method name is same just the parameters different.
		- e.g Constructor. Java Decides which Constructor to run during the compile time.
	2. Runtime/ Dynamic Polymorphism
		- Achieved by Method Overriding.i.e. that is function/method in parent and child class have same function name and body.
		- Which function will be called depends on the object type and what is accessible depend on the Type of the reference.   
		```java
		// Type of Reference =  Type Of Object
		Shapes obj    =    new Circle();
		```

2. What are the 4 pillars of OOPS?
	- Polymorphism
	- Inheritence
	-  Abstraction
	- Encapsulation

3. What is Abstraction?
	- Real Life Example : - Hiding the implementation part of the code like in java we have access to the System.out.prinln() but we don not need to know about how the println is woking internally that is abstraction. Similary In a car we need key to start the car we don't need to know how the car is getting started or engine works.
	- If a class have one or more abstract methods then it should be declared as abstract.
	- Abstract method only have name and parameter the body is not provided.  The Child class have to Override the Method of the parent class to provide the body.
    - Abstract class does not contain Abstract Constructors.  It can have constructors though. and the child class need to use super keyword to access it.  It can have instance variables but to initialize those we need to create constructor (note i do not say Absctract Constructors it's just a normal constructor here )either in child or parent class.
	- It can contain static methods.
	- It can have all access modifiers.

4. What is encapsulation?
	- The process of hiding the data in one entity or class is known as encapsulation. It is also known as data hiding.
	- It can be achieved by acces modifiers.
	- Real life example :- Capsul(Medicine) is a mixture of medicines stored in one containet known as capsul. We don't know what mixture of medicines are present inside the data it's hidden from us.

5. What is interface?
	- they have abstract functions (no body of functions).
	- Interface is like class but not completely. it is like an abstract class.  By default functions are public and abstract in interface.  variables are final and static by default in interface.
	- Interfaces specify only what the class is doing, not how it is doing it.
	- Using interface, you can specify a set of methods that can be implemented by one or more classes.
	- Although they are similar to abstract classes, interfaces have an additional capability:
	- A class can implement more than one interface. By contrast, a class can only inherit a single superclass  (abstract or otherwise).

6. What is Polymorphism?
	- Act of representing thing in multiple ways.

7. What is Object Oriented Programming and Procedural Programming?
	- Object Oriented Programming is used to solve real world problems.  object oriented means you're dealing with objects, procedural means you're dealing with procedures,which is another way to say linear execution of statements .if you have objects you can encapsulate those procedures in a more meanignful way  .but languages typically aren't fully OOP or fully procedural, they're usually a mix of the two with additional features sprinkled here and there  java is built around OOP principles but it's multi-paradigm




