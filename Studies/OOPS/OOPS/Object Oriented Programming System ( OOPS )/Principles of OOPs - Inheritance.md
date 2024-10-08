	##### Previous [[More About Static, Inner Classes and Singleton Class]]

To inherit a class in Java, you can use the `extends` keyword to incorporate the definition of one class into another. Here's an example of how to create a subclass that extends a superclass:

```java
class Superclass {
    // superclass members and methods
}

class Subclass extends Superclass {
    // subclass members and methods
}
```

In this example, the `Subclass` inherits all the members and methods from the `Superclass`. However, it cannot access the private members of the `Superclass`.

You can create a hierarchy of inheritance where a subclass becomes a superclass for another subclass. Java does not support multiple inheritance, so a subclass can have only one superclass.

When a reference to a subclass object is assigned to a superclass reference variable, you can only access the members defined by the superclass. Here's an example:

```java
Superclass superClassRef = new Subclass();
```

In the example above, `superClassRef` can only access the methods and members defined in the `Superclass`, even though it refers to an object of the `Subclass`.

You can use the `super` keyword in a subclass to refer to its immediate superclass. It has two general forms: one for calling the superclass constructor and another for accessing hidden members of the superclass. Here's an example:

```java
class Box {
    private double width;
    private double height;
    private double depth;

    // constructor
    Box(double w, double h, double d) {
        width = w;
        height = h;
        depth = d;
    }
}

class BoxWeight extends Box {
    private double weight;

    // constructor
    BoxWeight(double w, double h, double d, double m) {
        super(w, h, d); // calling superclass constructor
        weight = m;
    }
}
```

In the above example, the `BoxWeight` class extends the `Box` class. The `BoxWeight` constructor uses the `super` keyword to call the constructor of the `Box` class and initialize its own unique member `weight`.

The `super` keyword can also be used to access hidden members of the superclass. If a subclass has a member with the same name as a member in the superclass, the subclass can use `super.member` to access the hidden member of the superclass.

Additionally, the `final` keyword has three uses in inheritance:

1. Creating a named constant: You can use `final` to declare a variable as a constant, whose value cannot be changed.
2. Preventing method overriding: By using `final` before a method declaration, you can disallow the method from being overridden by subclasses.
3. Preventing class inheritance: By declaring a class as `final`, you prevent it from being inherited by other classes.

It's important to note that static methods can be inherited, but they cannot be overridden. Polymorphism does not apply to instance variables, only to methods.

I hope this helps to professionalize the explanation and provide examples. Let me know if you have any further questions!

## Super Keyword

The `super` keyword in Java is used to refer to the immediate superclass of a class. It can be used in several contexts to access or invoke the superclass's members, constructors, and methods. Here's an explanation of the `super` keyword and its notable points:

1. Accessing Superclass Members: The `super` keyword can be used to access the members (fields and methods) of the superclass. This is useful when a subclass has overridden a member, and you want to access the superclass's version of that member. For example:

```java
class Superclass {
    public int number = 10;
    
    public void display() {
        System.out.println("Superclass: " + number);
    }
}

class Subclass extends Superclass {
    public int number = 20;
    
    @Override
    public void display() {
        System.out.println("Subclass: " + number);
        System.out.println("Superclass: " + super.number);
    }
}

public class Main {
    public static void main(String[] args) {
        Subclass obj = new Subclass();
        obj.display();
    }
}
```

Output:
```
Subclass: 20
Superclass: 10
```

In the example above, the `Subclass` overrides the `display` method from the `Superclass`. Within the overridden method, the `super` keyword is used to access the `number` variable of the superclass, allowing both the subclass and superclass versions to be displayed.

2. Invoking Superclass Constructors: The `super` keyword can also be used to invoke the constructors of the superclass. This is useful when a subclass needs to initialize the inherited members from the superclass. The `super()` call must be the first statement in the constructor of the subclass. For example:

```java
class Superclass {
    public int number;

    public Superclass(int number) {
        this.number = number;
    }
}

class Subclass extends Superclass {
    public Subclass(int number) {
        super(number); // invoking superclass constructor
    }
}

public class Main {
    public static void main(String[] args) {
        Subclass obj = new Subclass(42);
        System.out.println(obj.number); // Output: 42
    }
}
```

In the example above, the `Subclass` invokes the constructor of the `Superclass` using `super(number)`. This allows the `number` parameter to be passed to the superclass constructor for initialization.

3. Calling Superclass Methods: The `super` keyword can be used to call the superclass's methods from within the subclass's methods. This is useful when a subclass wants to extend or modify the behavior of the superclass's method. For example:

```java
class Superclass {
    public void display() {
        System.out.println("Superclass display");
    }
}

class Subclass extends Superclass {
    @Override
    public void display() {
        super.display(); // calling superclass method
        System.out.println("Subclass display");
    }
}

public class Main {
    public static void main(String[] args) {
        Subclass obj = new Subclass();
        obj.display();
    }
}
```

Output:
```
Superclass display
Subclass display
```

In the example above, the `Subclass` overrides the `display` method of the `Superclass`. Within the overridden method, the `super.display()` call is used to invoke the superclass's `display` method before adding additional behavior.

Notable points about the `super` keyword:
- The `super` keyword cannot be used in a static context.
- The `super` keyword can only be used within the context of a subclass that is directly extending a superclass.
- The `super` keyword can access superclass members that are public or protected, but not private members.
- If the superclass has multiple constructors, the `super` keyword can be used to select a specific constructor to invoke in the subclass.

## Types of Inheritance

In Java, there are several types of inheritance, including:

1. Single Inheritance: Single inheritance refers to the scenario where a class extends only one superclass. Java supports single inheritance, allowing a class to inherit the properties and behavior of a single superclass. For example:

```java
class Superclass {
    // superclass members and methods
}

class Subclass extends Superclass {
    // subclass members and methods
}
```

2. Multilevel Inheritance: Multilevel inheritance occurs when a class extends another class, and that class, in turn, extends another class. Java supports multilevel inheritance, allowing you to create a hierarchy of classes. For example:

```java
class Grandparent {
    // grandparent members and methods
}

class Parent extends Grandparent {
    // parent members and methods
}

class Child extends Parent {
    // child members and methods
}
```

In the example above, the `Child` class inherits from the `Parent` class, which, in turn, inherits from the `Grandparent` class.

3. Hierarchical Inheritance: Hierarchical inheritance refers to a scenario where multiple classes extend a single superclass. Java supports hierarchical inheritance, allowing multiple subclasses to inherit from a common superclass. For example:

```java
class Superclass {
    // superclass members and methods
}

class Subclass1 extends Superclass {
    // subclass1 members and methods
}

class Subclass2 extends Superclass {
    // subclass2 members and methods
}
```

In the example above, both `Subclass1` and `Subclass2` inherit from the same `Superclass`.

4. Hybrid (Multiple and Hierarchical) Inheritance: Hybrid inheritance is a combination of multiple and hierarchical inheritance. It involves the inheritance of multiple classes as well as the inheritance of subclasses from a common superclass. Java does not support hybrid inheritance directly because it can lead to complications and ambiguity. However, you can achieve similar functionality using interfaces and multiple inheritance. By implementing multiple interfaces, a class can inherit behavior from multiple sources.

5. Multiple Inheritance: Multiple inheritance refers to a scenario where a class can inherit from multiple superclasses. However, Java does not support multiple inheritance of classes. This design decision was made to avoid complexities and ambiguities that can arise with multiple inheritance. Instead, Java supports multiple inheritance of interfaces, where a class can implement multiple interfaces to inherit different sets of behaviors.

To summarize, Java supports single inheritance, multilevel inheritance, and hierarchical inheritance. It does not support hybrid inheritance (directly) or multiple inheritance of classes. However, multiple inheritance of interfaces is supported in Java.

If you need to achieve functionality similar to multiple inheritance of classes, you can use interfaces in combination with single inheritance or hierarchies to implement the desired behavior.

##### Next [[Principles of OOPs - Polymorphism]]

