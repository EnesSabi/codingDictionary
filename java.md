# Java

```java
public class Main {
  public static void main(String[] args) {
    System.out.println("Hello World");
  }
}
```

## Datatypes
### Primitive data types
```java
datatyp varname = value;    // Blueprint
int myNum = 5;              // Integer
float myFloatNum = 5.99f;   // Floating point number
double myDoubleNum = 9.98;  // Double
char myLetter = 'd';        // Character
boolean myBool = true;      // Boolean
```
### Non-primitive data types
```java
String myText = "Hello";    // String
int[] myNum = {10,20,30};   // Arrays
public class main {
    int x = 69;
}                           // Classes
```

## Casting
```java
byte < short < char < int < long < float < double   //automatic widening cast
double -> float -> long -> int -> char -> short -> byte //manual narrowing cast
--------------------------------------
//Automatic widening cast
short shortNum = 69;
double doubleNum = shortNum;
System.out.println(intNum); //Output is 69.0
//Manual narrowing cast
double doubleNum = 69.0;
short shortNum = (short) doubleNum;
System.out.println(shortNum); //Output is 69
```
## Operators
Java divides the operators into these following five groups:
### Arithmetic
|Operator   |Name   |Example  |
|-----------|-------|--------------|
|+   |Addition   |``` x + y ```   |
|-   |Subtraction   |``` x - y ```   |
|*   |Multiplication   |``` x * y ```   |
|/   |Division   |``` x / y ```   |
|%   |Modulus   |``` x % y```   |
|++   |Increment   |``` i++ ```   |
|--   |Decrement   |``` i-- ```   |
### Assignment
|Operator   |Same As   |Example   |
|-----------|-------|--------------|
|=   |``` x = 69 ```   |``` x = 69 ```   |
|+=   |``` x = x + 69 ```   |``` x += 69 ```   |
|-=   |``` x = x - 69 ```   |``` x -= 69 ```   |
|*=   |``` x = x * 69 ```   |``` x *= 69 ```   |
|/=   |``` x = x / 69 ```   |``` x /= 69 ```   |
|%=   |``` x = x % 69 ```   |``` x %= 69 ```   |
|&=   |``` x = x & 69 ```   |``` x &= 69 ```   |
||=   |``` x = x | 69 ```   |``` x |= 69 ```   |
|^=   |``` x = x ^ 69 ```   |``` x ^= 69 ```   |
|>>=   |``` x = x >> 69 ```   |``` x >>= 69 ```   |
|<<==   |``` x = x << 69 ```   |``` x <<= 69 ```   |
### Comparison
|Operator   |Name   |Example   |
|-|-|-|-|
|==   |``` Equal ```   |``` x == y ```   |
|!=   |``` Not Equal ```   |``` x != y ```   |
|>   |``` Greater than ```   |``` x > y ```   |
|<   |``` Less than ```   |``` x < y ```   |
|>=   |``` Greater than or equal ```   |``` x >= y ```   |
|<=   |``` Less than or equal ```   |``` x <= y ```   |
### Logical
|Operator   |Name   |Example   |Description
|-|-|-|-|
|&&   |logical and   |``` x && y  ```   |true if statements are true   |
|I   |logical or   |``` x II y ```   |true if one or many true   |
|!   |logical not   |``` !(x && y) ```   |reverse result
### Bitwise
|Operator   |Name   |Example   |
|-----------|-------|--------------|
|int a = 5;   |int b = 7;| 0b5 = 101 0b7 = 111
|&   |Bitwise AND   |``` a&b -> 5 ``` 0101 & 0111 = 0101   |
|I   |Bitwise OR   |``` a|b -> 7 ``` 0101 | 0111 = 0111   |
|^   |Bitwise XOR   |``` a^b -> 2 ``` 0101 ^ 0111 = 0010  |
|~   |Bitwise Complement   |``` ~a -> -6 // ``` ~0101 = 1010 |      

Caution with the Bitwise Complement because 1010 is in normal binary to decimal 10, but you need to use the 1's complementary reading.
If you want to solve fast squares and square roots shiftoperators are very useful

## Strings
Strings are always surrounded by double quotation marks!
### methods
|Method|Explanation
|-|-|
|String txt = "Hello World!"   |Syntax
|txt.length();   |Length of the String
|txt.toUpperCase();   |Every character to upper case
|txt.toLowerCase();   |and vice versa
|txt.indexOf("Hello");   |returns the index of the first occurrence of this specified string
|txt.concat(txt);   | concatenate two strings **without whitespaces between**
Concatenation with "+" adds integers and concatenates Strings

### special escape characters
|Escape character   | Result   | Description   |
|-|-|-|
|\'   |'   |Single quote
|\"   |"   |Double quote  
|\\   |\   |Backslash
|\n   |    |New Line
|\r   |    |Carriage return
|\t   |    |Tab
|\b   |    |Backspace
|\f   |    |Form Feed

## math
|Methods   |Explanation   |
|-|-|
|Math.max(5,10);   |find the highest value   |
|Math.min(5,10);   |find the lowest value   |
|Math.sqrt(64);   |square root of 64   |
|Math.abs(-6.9);   |absolute value   |
|Math.random()*69;   |exclusive max number   |

## Conditions
### if Statement
```java
if(condition) {/*executable code if true*/}
```
### if else Statement
```java
if(condition) {/*executable code if true*/}
else {/*executable code if false*/}
```
### else-if Statement
```java
if(condition1) {/*executable code if condition1 is true*/}
else if(condition2) {/*executable code if condition2 true*/}
else {/*executable code if false*/}
```
### short if else Statement
```java
datatype varNam = (condition) ? /*returns if true*/ : /*returns if false*/
```
### switch
```java
switch(expression) {
  case x: /*code block*/ break;
  case y: /*code block*/ break;
  default: /*code blocks*/ break;
}
```
## Loops
### while loop
```java
while (condition) {/*code block*/}
```
### do-while loop
```java
do {/* code block to be executed*/}
while (condition);
```
### for loop 
```java
for (statement 1; statement 2; statement 3)
{/* code block to be executed*/}
```
### for-each loop 
```java
for (type varNam : arrayName)
{/* code block to be executed*/}
```
## Arrays
declare an array with square brackets immediately after the type declaration.
array indexes starts with 0.
```java 
datatypes[] varNam = {values}; 
```
### methods
```java
String[] cars = {"Lamborghini", "Volkswagen", "Königsegg", "Peugeot"};
System.out.println(cars.length());
//to iterate use for-each loop for better readability
for (String i : cars) {
  System.out.println(i);
}
```
### multidimensional arrays
```java
int[][] myNumbers = {{1,2,3,4},{5,6,7}};
System.out.println(myNumbers[1][2]);
```
if you want to iterate over multidimensional arrays you need to use nested for loops
```java
for (int i = 0; i < myNumbers.length; ++i) {
  for(int j = 0; j < myNumbers[i].length; ++j) {
    System.out.println(myNumbers[i][j]);
  }
}
```
## Methods
Methods are a block of code which run if called, also known as functions.
If you need to reuse code, define the code once and use it many times.
To create a methode it needs to be created within a class. The class defines the visiblity. Defining a method needs 3 main components:
1. ```static``` means that the method belongs to the class and is not an object of this class.
2. Return type, which could be void if it doesn't have a return value
3. ```methodname()``` is the name of the method followed by two paired parentheses.

## Keywords
### super
The keyword super is used in the class constructor to call the constructor of the superclass.
Similarly, the super keyword can also be used to call other members (fields, methods) of the superclass, for example, super.someMethod() would call the someMethod() of the superclass.


## Classes
Java uses classes to defines objects that encapsulate data and behavior.
A class is defined by its keyword ```class```, instance variables and methods, bt only the class definition is mandatory.
```java
public class ClassName {  //Class code is placed inside of the curled braces
  //instances variables which hold the state for an object and should normally be private or protected
  private int classInt;
  private String classString;
  //constructor for object-orientation always public
  //There are many possiblities to define constructors and you could handle different object calls
  public ClassName(int inputInt, String inputString) {
    classInt = inputInt;
    classString = inputString;
    //if the instance varibale names and the method parameter have the same name: the object variable needs the this. operator
    //this.classInt = classInt;
  } //end of constructor
  //methods of the class
  public void doSomething() {
    System.out.println("Doing something...");
  }
} //end of class
```
If you want to create objects of this class you need to use the ```new``` operator and arguments as the constructors. To access the instance variable or methods it is necessary to create an object.
```java
ClassName classNameObject = new ClassName(42, "Hello");
classNameObject.doSomething();
```

## Exceptions
Java exceptions are a mechanism for handling errors and exceptional conditions that may occur during the execution of a Java program. When an error or an exceptional condition is encountered during program execution, an exception object is created and thrown by the Java Virtual Machine.
Java exceptions are divided into two categories: checked exceptions and unchecked exceptions. 
Checked exceptions are exceptions that the compiler requires you to catch or declare in the method signature. These exceptions are typically used for conditions that the program can recover from.
Unchecked exceptions, on the other hand, are exceptions that do not have to be caught or declared in the method signature. They are typically used for conditions that the program cannot recover from.
To handle exceptions in Java, you use try-catch blocks. A try block contains the code that might throw an exception, while a catch block contains the code that handles the exception. Multiple catch blocks can be chained together to handle different types of exceptions. You can also include a finally block that contains code that should be executed whether or not an exception is thrown.
### Examples for checked and unchecked exceptions
#### Checked Exceptions:
  1. IOException: This exception is thrown when an input or output operation fails or is interrupted. It is a checked exception, which means that any method that can throw an IOException must declare it in its method signature or handle it with a try-catch block.
  2. SQLException: This exception is thrown when an error occurs while accessing a database using JDBC. It is also a checked exception, which means that any method that can throw an SQLException must declare it in its method signature or handle it with a try-catch block.
  3. ClassNotFoundException: This exception is thrown when an attempt is made to load a class at runtime using Class.forName(), but the class cannot be found. It is a checked exception.
#### Unchecked Exceptions:
  1. NullPointerException: This exception is thrown when an attempt is made to access a null reference. It is an unchecked exception, which means that it does not have to be caught or declared in the method signature.
  2. ArrayIndexOutOfBoundsException: This exception is thrown when an attempt is made to access an array with an invalid index. It is also an unchecked exception.
  3. IllegalArgumentException: This exception is thrown when an illegal argument is passed to a method. It is an unchecked exception.
### Java Exceptions
The try block tries to do something which can throw an Exception
The catch block catches the exception and prints an error message.
```Java
try {
    //do something critical or use something critical
} catch (Exception e){
    System.out.println("An Exception is thrown: " + e.getMessage());
}
```
### Custom Exceptions
You can create your own exceptions in Java by extending the Exception or RuntimeException classes.
``` Java
public class CustomException extends Exception {
    public CustomException(String message) {
        super(message);
    }
}
```
### Chained Exceptions
Sometimes it is useful to wrap one exception inside another exception, to provide additional context or information about the error.
```Java
try {
    // some code that throws an exception
} catch (Exception e) {
    throw new RuntimeException("An error occurred", e);
}
```
### Multiple Exceptions
You can use multiple catch blocks to handle different types of exceptions.

```Java
try {
    // some code that throws an exception
} catch (IOException e) {
    System.out.println("An IO exception occurred: " + e.getMessage());
} catch (SQLException e) {
    System.out.println("An SQL exception occurred: " + e.getMessage());
} catch (Exception e) {
    System.out.println("An unknown exception occurred: " + e.getMessage());
}
```
## Object-Orientation
Object-oriented programming (OOP) is a programming paradigm that is based on the concept of "objects", which can contain data and code to manipulate that data. Java is an object-oriented programming language, and as such, it supports the following OOP concepts: Encapsulation, Inheritance, Polymorphism, Abstraction/Interfaces.
### Encapsulation
This is the practice of bundling data and the methods that manipulate that data into a single unit, called a class. In Java, the class is the fundamental unit of encapsulation.
```Java
public class Person {
    private String name;
    private int age;

    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }
    public String getName() {
        return name;
    }
    public int getAge() {
        return age;
    }
    public void setName(String name) {
        this.name = name;
    }
    public void setAge(int age) {
        this.age = age;
    }
}
```
In this code, we have a Person class that has two private fields: name and age. These fields are not directly accessible from outside the class. Instead, we have public getter and setter methods that allow us to access and modify the fields. By doing this, we can ensure that the data is only accessed and modified in a controlled way, which can make our code more robust and easier to maintain.
### Inheritance
This is a mechanism that allows one class to inherit the properties (data and methods) of another class. In Java, inheritance is implemented using the extends keyword.
```Java
public class Animal {
    private String name;
    
    public Animal(String name) {
        this.name = name;
    }
    public void makeSound() {
        System.out.println("Animal is making a sound.");
    }
}
public class Dog extends Animal {
    public Dog(String name) {
        super(name);
    }
    public void makeSound() {
        System.out.println("Woof!");
    }
}
public class Main {
    public static void main(String[] args) {
        Animal animal = new Animal("Generic Animal");
        animal.makeSound(); // outputs "Animal is making a sound."
        
        Dog dog = new Dog("Rover");
        dog.makeSound(); // outputs "Woof!"
        
        Animal dogAsAnimal = new Dog("Rover");
        dogAsAnimal.makeSound(); // outputs "Woof!" even though the reference is to an Animal object
        // More code...
    }
}
```
In this code, we have two classes: Animal and Dog. Dog is a subclass of Animal, which means that it inherits the properties (in this case, the name field and the makeSound() method) of Animal. However, Dog overrides the makeSound() method to provide its own implementation. We demonstrate inheritance by creating an Animal object and a Dog object, and then assigning the Dog object to an Animal reference. When we call makeSound() on the Animal reference that points to a Dog object, the Dog implementation of makeSound() is called.
### Polymorphism
This is the ability of objects of different classes to be treated as if they are of the same type. In Java, polymorphism is implemented through method overloading and method overriding.
```Java
```
### Abstraction/ Interfaces
This is the process of hiding implementation details and exposing only the essential features of an object. In Java, this can be achieved through abstract classes and interfaces.
```Java
```
## Collections

## Generics and Lambdas (Functional programming)

## I/O