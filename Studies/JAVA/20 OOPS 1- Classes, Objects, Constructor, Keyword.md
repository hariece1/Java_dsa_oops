- A class is named group of properties and function.
- ==**A class is a template for an object, and an object is an instance of a class.**==
- A class creates a new data type that can be used to create objects.


Variable defines object is know as reference variable
Instance variable - variable inside the object is known as instance variable
***new - dynamically allocates memory at run time***

Class is a logical constructor 
Object is a physical reality     -- Occupy space in memory






**.operator** - is used to link reference variable to instance variable

Maruti.price - Maruti reference variable and price is instance variable.

**Constructor**
		Constructor is special type of function that runs when you create a object and it allocates some variables.
		
---
		- Constructor is used **to create the instance of the class**. Constructors are almost similar to methods except for two things - 
			 Its name is the same as the class name and it has ==no return type==.
		- The constructor doesn't have a return type **because it is not directly called by our code**. Instead, it is called by the runtime system.

	
**The this keyword refers to the ==current object== in a method or constructor. The most common use of the this keyword is to eliminate the confusion between class attributes and parameters with the same name**

This keyword place this with name of the reference variable


In java primitive data(Integer, Char, Boolean, Float) types are not Implemented as object.

Object are stored heap memory since primitives are not object they are stored in stack


**Wrapper class**

 Wrapper classes are used to treat primitive data types as objects.


```
Integer num =45;
```

As it changed to object is has so many function like( toString, equals, float value etc..)

C:\Users\HP\IdeaProjects\java

https://www.youtube.com/watch?v=zvR-Oif_nxg