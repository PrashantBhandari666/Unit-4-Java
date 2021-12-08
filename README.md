# Inheritance & Packaging

## Inheritance
------------------------

Inheritance is an important pillar of OOP ``(Object-Oriented Programming)`` . It is the mechanism in java by which one class is allowed to inherit the features ``(fields and methods)`` of another class. 

### **Types of Inheritance in Java**

Below are the different types of inheritance which are supported by Java. 

* Single Inheritance
* Multilevel Inheritance
* Hierarchical Inheritance
* Multiple Inheritance
* Hybrid Inheritance

#### **Single Inheritance:**

In single inheritance, subclasses inherit the features of one superclass. 

Example:

```Java
class A {
    public void print_A()
    {
        System.out.println("This is Class A.");
    }
}
class B extends A {
    public void print_B()
    {
        System.out.println("This is Class B.");
    }
}
public class single {
    public static void main(String[] args)
    {
         B m= new B();
         m.print_A();
         m.print_B();
    }
}
```

Output:
```
This is Class A.
This is Class B.
```

#### **Multilevel Inheritance:**

In Multilevel Inheritance, a derived class will be inheriting a base class and as well as the derived class also act as the base class to other class. In the below image, class A serves as a base class for the derived class B, which in turn serves as a base class for the derived class C. In Java, a class cannot directly access the grandparent’s members.

Example:

```Java
class A {
    public void print_A()
    {
        System.out.println("This is Class A.");
    }
}
class B extends A {
    public void print_B()
    {
        System.out.println("This is Class B.");
    }
}
class C extends B {
    public void print_C()
    {
        System.out.println("This is Class C.");
    }
}
public class multilavel {
    public static void main(String[] args)
    {
        C m= new C();
        m.print_A();
        m.print_B();
        m.print_C();
    }
}

```

Output:
```
This is Class A.
This is Class B.
This is Class C.
```

#### **Hierarchical Inheritance:**

In Hierarchical Inheritance, one class serves as a superclass (base class) for more than one subclass.

Example:

```Java
class A {
    public void print_A()
    {
        System.out.println("This is Class A.");
    }
}
class B extends A {
    public void print_B()
    {
        System.out.println("This is Class B.");
    }
}
class C extends A {
    public void print_C()
    {
        System.out.println("This is Class C.");
    }
}
class D extends A {
    public void print_D()
    {
        System.out.println("This is Class D.");
    }
}
public class Hierarchical {
    public static void main(String[] args) {
        B m1 = new B();
        m1.print_A();
        m1.print_B();
        C m2 = new C();
        m2.print_A();
        m2.print_C();
        D m3 = new D();
        m3.print_A();
        m3.print_D();
    }
}
```

Output:
```
This is Class A.
This is Class B.
This is Class A.
This is Class C.
This is Class A.
This is Class D.
```

#### **Multiple Inheritance (Through Interfaces):**

In Multiple inheritances, one class can have more than one superclass and inherit features from all parent classes. Please note that Java does not support multiple inheritances with classes. In java, we can achieve multiple inheritances only through Interfaces.

Example:

```Java
interface A {
    public void print_Apple();
}
interface B {
    public void print_Ball();
}
interface C extends A,B {
    public void print_Cat();
}
class D implements C {
    public void print_Apple()
    {
        System.out.println("Apple");
    }
    public void print_Ball()
    {
        System.out.println("Ball");
    }
    public void print_Cat()
    {
        System.out.println("Cat");
    }
}
public class multiple {
    public static void main(String[] args) {
        D m= new D();
        m.print_Apple();
        m.print_Ball();
        m.print_Cat();
    }
}
```

Output:
```
Apple
Ball
Cat
```

#### **Hybrid Inheritance(Through Interfaces):**

It is a mix of two or more of the above types of inheritance. Since java doesn’t support multiple inheritances with classes, hybrid inheritance is also not possible with classes. In java, we can achieve hybrid inheritance only through Interfaces. 

Example:

```Java
interface A {
    public void print_Apple();
}
interface B extends A {
    public void print_Ball();
}
interface C extends A {
    public void print_Cat();
}
interface D extends A {
    public void print_Dog();
}
class hybrid implements B, C, D {
    public void print_Apple()
    {
        System.out.println("Apple");
    }
    public void print_Ball()
    {
        System.out.println("Ball");
    }
    public void print_Cat()
    {
        System.out.println("Cat");
    }
    public void print_Dog()
    {
        System.out.println("Dog");
    }
    public static void main(String [] args) {
        hybrid m = new hybrid();
        m.print_Apple();
        m.print_Ball();
        m.print_Cat();
        m.print_Dog();
    }
}
```

Output:
```
Apple
Ball
Cat
Dogs
```

### **Using ``extends`` keyword**

``extends`` is the keyword used to inherit the properties of a class. Following is the syntax of extends keyword :

Syntax:

```Java
class <derived-class> extends <base-class>  
{  
   //methods and fields  
}  
```

### **Subclass and Superclass**

In Java, it is possible to inherit attributes and methods from one class to another. We group the "inheritance concept" into two categories:

* ``Subclass (child)`` - the class that inherits from another class.
* ``Superclass (parent)`` - the class being inherited from.

To inherit from a class, use the ``extends`` keyword.

### **``super`` keyword usage**

The ``super`` keyword refers to superclass (parent) objects. It is used to call superclass methods, and to access the superclass constructor.The most common use of the ``super`` keyword is to eliminate the confusion between superclasses and subclasses that have methods with the same name.

* ``super`` can be used to refer immediate parent class instance variable.
* ``super`` can be used to invoke immediate parent class method.
* ``super()`` can be used to invoke immediate parent class constructor.

**Differentiating the Members:**

If a class is inheriting the properties of another class. And if the members of the superclass have the names same as the sub class, to differentiate these variables we use super keyword as shown below.

```Java
super.variable
super.method();
```

### **Overriding Method**
If subclass (child class) has the same method as declared in the parent class, it is known as method overriding in Java.

In other words, If a subclass provides the specific implementation of the method that has been declared by one of its parent class, it is known as method overriding.

**Usage of Java Method Overriding**

* Method overriding is used to provide the specific implementation of a method which is already provided by its superclass.
* Method overriding is used for runtime polymorphism

**Rules for Java Method Overriding**

* The method must have the same name as in the parent class
* The method must have the same parameter as in the parent class.
* There must be an IS-A relationship (inheritance).

Example:

```Java
class A 
{
	void Print()
	{
		System.out.println("This is Class A");
	}
}
class B extends A
{
   @Override
	void Print()
	{
		System.out.println("This is Class B");
	}
}
class C extends B
{
   @Override
	void Print()
	{
		System.out.println("This is Class C");
	}
}
class main 
{
	public static void main(String[] args)
	{
      A a = new A();
      a.Print();
      B b = new B();
      b.Print();
      C c = new C();
      c.Print();
	}
}
```

Output:
```
This is Class A
This is Class B
This is Class C
```

### **Dynamic Method Dispatch**
Dynamic method dispatch is a mechanism by which a call to an overridden method is resolved at runtime. This is how java implements runtime polymorphism. When an overridden method is called by a reference, java determines which version of that method to execute based on the type of object it refer to. In simple words the type of object which it referred determines which version of overridden method will be called.

```Java
class A
{
	void m1()
	{
		System.out.println("Inside A's m1 method");
	}
}
class B extends A
{
	// overriding m1()
	void m1()
	{
		System.out.println("Inside B's m1 method");
	}
}
class C extends A
{
	// overriding m1()
	void m1()
	{
		System.out.println("Inside C's m1 method");
	}
}
class Dispatch
{
	public static void main(String args[])
	{
		// object of type A
		A a = new A();
		// object of type B
		B b = new B();
		// object of type C
		C c = new C();
		// obtain a reference of type A
		A ref;
		// ref refers to an A object
		ref = a;
		// calling A's version of m1()
		ref.m1();
		// now ref refers to a B object
		ref = b;
		// calling B's version of m1()
		ref.m1();
		// now ref refers to a C object
		ref = c;
		// calling C's version of m1()
		ref.m1();
	}
}
```

Output:
```
Inside A's m1 method
Inside B's m1 method
Inside C's m1 method
```

## The Object Class:
-------------------------
Object is the mother of all classes , in other words  every other class in java is the subclass of Object class. Object class is in the default package i.e ``java.lang`` package .

The Object class defines the basic state and behavior that all objects must have, such as the ability to compare oneself to another object, to convert to a string, to wait on a condition variable, to notify other objects that a condition variable has changed, and to return the object's class.There are 11 methods in Object class .

It has following methods in its class:

* ``equals(Object obj)``: Checks whether the obj object is equal to the object on which the equals method is called .

* ``hashCode()``: ``hashCode()`` is used for the HashTable.It returns the hash value of the object.

* ``getClass()``: It returns the runtime class object .

* ``clone()``: It creates and  returns the copy of the object .    

* ``notify()``: It will wake up the thread waiting for the objects monitor.

* ``notifyAll()``: It will wakes up all the thread that are waiting for the objects monitor .

* ``toString()``: It will return the string representation of the object .

* ``wait()``: This method causes the current thread to place itself in the wait set for this object and then to relinquish any and all synchronization claims on this object

## Abstract and Final Class in Java
------------------------------------

### Abstract Class
A class which is declared as abstract is known as an abstract class. It can have abstract and non-abstract methods. It needs to be extended and its method implemented. It cannot be instantiated.

**Syntax of declaring an abstract class:**

To declare an abstract class we use the keyword ``abstract``. The syntax is given below:

```Java
abstract class ClassName
{
    //class body
}
```

**Example:**

```Java
abstract class A{}  
```

### Final Class
A class which is declared with the ``Final`` keyword is known as the final class. The ``final`` keyword is used to finalize the implementations of the classes, the methods and the variables used in this class. The main purpose of using a final class is to prevent the class from being inherited (i.e.) if a class is marked as final, then no other class can inherit any properties or methods from the final class. If the final class is extended, Java gives a compile-time error.

The following is an example of how a final class is declared. However, a compile-time error is given because this final class is being inherited.

```Java
// Java program to demonstrate the
// Final class
final class Super {
	private int data = 100;
}
public class Sub extends Super {
	public static void main(String args[])
	{
	}
}
```

The following table demonstrates the difference between an ``abstract`` class and a ``final`` class:

|                         Abstract Class                             |                                 Final Class                                    |
|--------------------------------------------------------------------|--------------------------------------------------------------------------------|
|Uses the ``abstrac`` key word.                                      |Uses the ``final`` key word.                                                    |
|This helps to achieve abstraction.                                  |This helps to restrict other classes from accessing its properties and methods. |
|For later use, all the abstract methods should be overridden        |Overriding concept does not arise as final class cannot be inherited            |
|A few methods can be implemented and a few cannot                   |All methods should have implementation                                          |
|Cannot create immutable objects (infact, no objects can be created) |Immutable objects can be created (eg. String class)                             |
|Abstract class methods functionality can be altered in subclass     |Final class methods should be used as it is by other classes                    |
|Can be inherited                                                    |Cannot be inherited                                                             |
|Cannot be instantiated                                              |Can be instantiated                                                             |

## Packages in Java:
-----------------------
Packages are used in Java in order to prevent naming conflicts, to control access, to make searching/locating and usage of classes, interfaces, enumerations and annotations easier, etc.
A Package can be defined as a grouping of related types (classes, interfaces, enumerations and annotations ) providing access protection and namespace management.

### **Defining a packages:**
We use the ``package`` keyword to create or define a package in java programming language.

Syntax:
```Java
package packagename;
```

Let's consider the following code to create a user-defined package ``examplepackage``.

```Java
package examplepackage;
public class DefiningPackage {
	public static void main(String[] args) {
		System.out.println("This class belongs to examplepackage.");
	}
}
```

Now, save the above code in a file ``DefiningPackage.java``, and compile it using the following command.

```
javac -d . DefiningPackage.java
```

The above command creates a directory with the package name ``examplepackage``, and the ``DefiningPackage.class`` is saved into it.

Run the program use the following command.

```
java examplepackage.DefiningPackage
```

### **Importing a Package:**

In java, the ``import`` keyword used to import built-in and user-defined packages. When a package has imported, we can refer to all the classes of that package using their name directly.

The import statement must be after the package statement, and before any other statement.

Using an ``import`` statement, we may import a specific class or all the classes from a package.

**Importing specific class**

Using an importing statement, we can import a specific class. The following syntax is employed to import a specific class.

Syntax:

```Java
import packageName.ClassName;
```

**Importing all the classes**

Using an importing statement, we can import all the classes of a package. To import all the classes of the package, we use * symbol. The following syntax is employed to import all the classes of a package.

Syntax:

```Java
import packageName.*;
```

**Consider the following import statement**

```Java
import java.util.*;
```

The above import statement ``util`` is a sub-package of ``java`` package. It imports all the classes of ``util`` package only, but not classes of ``java`` package.

## Interface
---------------------
Like a class, an interface can have methods and variables, but the methods declared in an interface are by default abstract (only method signature, no body).  

* Interfaces specify what a class must do and not how. It is the blueprint of the class.
* An Interface is about capabilities like a Player may be an interface and any class implementing Player must be able to (or must implement) move(). So it specifies a set of methods that the class has to implement.
* If a class implements an interface and does not provide method bodies for all functions specified in the interface, then the class must be declared abstract.
* A Java library example is, Comparator Interface. If a class implements this interface, then it can be used to sort a collection.

### **Defining a Interface:**
An interface is declared by using the ``interface`` keyword. It provides total abstraction; means all the methods in an interface are declared with the empty body, and all the fields are public, static and final by default. A class that implements an interface must implement all the methods declared in the interface.

**Syntax:**

```Java
interface <interface_name>{            
    // declare constant fields  
    // declare methods that abstract   
    // by default.  
}  
```

**Example:**

```Java
interface Player
{
    final int id = 10;
    int move();
}
```

### **Implementing and Applying Interfaces:**
To implement an interface we use keyword ``implements``.

**Syntax:**

```Java
class <class_name> implements <interface_name>
```

**Example:**

```Java
class main implements Player
```

**Example Program:**
Let’s consider the example of vehicles like bicycle, car, bike………, they have common functionalities. So we make an interface and put all these common functionalities. And lets Bicycle, Bike, car ….etc implement all these functionalities in their own class in their own way.

```Java
import java.io.*;
interface Vehicle {
	// all are the abstract methods.
	void changeGear(int a);
	void speedUp(int a);
	void applyBrakes(int a);
}
class Bicycle implements Vehicle{
	int speed;
	int gear;
	// to change gear
	@Override
	public void changeGear(int newGear){
		gear = newGear;
	}
	// to increase speed
	@Override
	public void speedUp(int increment){	
		speed = speed + increment;
	}
	// to decrease speed
	@Override
	public void applyBrakes(int decrement){
		speed = speed - decrement;
	}
	public void printStates() {
		System.out.println("speed: " + speed + " gear: " + gear);
	}
}
class Bike implements Vehicle {
	int speed;
	int gear;
	// to change gear
	@Override
	public void changeGear(int newGear){
		gear = newGear;
	}
	// to increase speed
	@Override
	public void speedUp(int increment){
		speed = speed + increment;
	}
	// to decrease speed
	@Override
	public void applyBrakes(int decrement){
		speed = speed - decrement;
	}
	public void printStates() {
		System.out.println("speed: " + speed + " gear: " + gear);
	}
}
class GFG {
	public static void main (String[] args) {
		// creating an inatance of Bicycle
		// doing some operations
		Bicycle bicycle = new Bicycle();
		bicycle.changeGear(2);
		bicycle.speedUp(3);
		bicycle.applyBrakes(1);
		System.out.println("Bicycle present state :");
		bicycle.printStates();
		// creating instance of the bike.
		Bike bike = new Bike();
		bike.changeGear(1);
		bike.speedUp(4);
		bike.applyBrakes(3);
		System.out.println("Bike present state :");
		bike.printStates();
	}
}
```
**Output:**
```
Bicycle present state :
speed: 2 gear: 2
Bike present state :
speed: 1 gear: 1
```
