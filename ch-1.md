## Java is an object-oriented, class-based, concurrent, secured and general-purpose computer-programming language.
---
## OOPs 
`Object-Oriented Programming` is a methodology or paradigm to design a program using classes and objects.\
It simplifies software development and maintenance by providing some concepts:

- **Object** 
    - Any entity that has state and behavior is known as an object. ex- chair, pen.
    - An Object can be defined as an instance of a class.
    - An object contains an address and takes up some space in memory

- **Class** - 
    - Collection of objects is called class. It is a logical entity.
    - A class can also be defined as a blueprint from which you can create an individual object. 
    - Class doesn't consume any space.

- **Inheritance** - 
    - When one object acquires all the properties and behaviors of a parent object.
    - It provides code reusability. It is used to achieve runtime polymorphism.

- **Polymorphism** - 
    - If one task is performed in different ways
    - we use method overloading and method overriding to achieve polymorphism.

- **Abstraction** - 
    - Hiding internal details and showing functionality is known as abstraction.
    - In java, we use abstract class and interface to achieve abstraction.

- **Encapsulation** - 
    - Binding (or wrapping) code and data together into a single unit are known as encapsulation.
    - A java class is the example of encapsulation. Java bean is the fully encapsulated class because all the data members are private here.

Apart from these concepts, there are some other terms which are used in Object-Oriented design:

- **Coupling** - 
    - Coupling refers to the knowledge or information or dependency of another class.
    - It arises when classes are aware of each other. 
    - If a class has the details information of another class, there is strong coupling.
    - We can use interfaces for the weaker coupling
    
- **Cohesion** - 
- **Association** - 
- **Aggregation** - 
- **Composition** - 

---

- **Object**
    - An entity that has state and behavior is known as an object e.g., chair, bike, marker, pen, table, car, etc
    - An object is an instance of a class. A class is a template or blueprint from which objects are created.
    - It has three characterstics
        - ***State*** : represents the data (value) of an object.
        - ***Behavior***: represents the behavior (functionality) of an object such as deposit, withdraw, etc.
        - ***Identity***: An object identity is typically implemented via a unique ID. The value of the ID is not visible to the external user. However, it is used internally by the JVM to identify each object uniquely.

- **Classes** 
    - Blueprint from which obejct is created, it has  ***fields, Methods, Constructors, Blocks, Nested class and interface***

```java
class Student{ 
 int id;    //data member or instance variable  ,  memory allocated at runtime

 String name;  
 
 public static void main(String args[]){  
    
  Student s1=new Student(); 
  System.out.println(s1.id);  
 }  
}  
```



## `Java main() method`
Without main() methode program will compile, but not run.
main() methode is static because its not  required to make object to call. Ex. Class_Name.main()

```java
    public static void main(String args[])  
    static public void main(String[] args)  
    static public void main(String...args)  
-----------------------------
class Example{
    static {  
        System.out.println("Static block");  
    }  
    public static void main(String args[]){  
        System.out.println("Static method");  
    }  
}
-- Output --
Static block
Static method
```
#### `A valid java program`
it will compile and run without error
```java
    abstract class DemoNoMain extends javafx.application.Application  {  
        static{  
            System.out.println("Java");  
            System.exit(0);  
        }  
    }  
```

## Methods
-   Predefined Method / standard library method / built-in method.
-   User-defined Method

#### `static Methode`
It can call without creating object of class; Note- Its not require that all methode in class should be static.


```java
    class Example{
    public static void main(String args[]){  
        MyClass.staticMethode();
        MyClass myClass = new MyClass();
        MyClass.nonStaticMethode();//Invalid XXXXX
        myClass.staticMethode();   //Invalid XXXXX
    }  
    }
    class MyClass{
        static int a = 10;
        public static void staticMethode(){System.out.println("static")} //Static Method
        public void nonStaticMethode(){System.out.println("non static")} //Instance Method
    }
// --------------
    class Example{
    public static void main(String args[]){  
        MyClass myClassObject = new MyClass();
        MyClass.a = 20;
        System.out.println(myClassObject.a)
    }  
    }
    // -- output ---
    // 20
```

