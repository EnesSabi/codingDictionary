# Java

```java
public class Main {
  public static void main(String[] args) {
    System.out.println("Hello World");
  }
}
```

## Datatype
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
| Operator | Name           | Example       |
|----------|----------------|---------------|
| +        | Addition       | ``` x + y ``` |
| -        | Subtraction    | ``` x - y ``` |
| *        | Multiplication | ``` x * y ``` |
| /        | Division       | ``` x / y ``` |
| %        | Modulus        | ``` x % y```  |
| ++       | Increment      | ``` i++ ```   |
| --       | Decrement      | ``` i-- ```   |
### Assignment
| Operator | Same As             | Example          |
|----------|---------------------|------------------|
| =        | ``` x = 69 ```      | ``` x = 69 ```   |
| +=       | ``` x = x + 69 ```  | ``` x += 69 ```  |
| -=       | ``` x = x - 69 ```  | ``` x -= 69 ```  |
| *=       | ``` x = x * 69 ```  | ``` x *= 69 ```  |
| /=       | ``` x = x / 69 ```  | ``` x /= 69 ```  |
| %=       | ``` x = x % 69 ```  | ``` x %= 69 ```  |
| &=       | ``` x = x & 69 ```  | ``` x &= 69 ```  |
|          | =                   | ``` x = x        | 69 ```   |``` x |= 69 ```   |
| ^=       | ``` x = x ^ 69 ```  | ``` x ^= 69 ```  |
| >>=      | ``` x = x >> 69 ``` | ``` x >>= 69 ``` |
| <<==     | ``` x = x << 69 ``` | ``` x <<= 69 ``` |
### Comparison
|Operator   |Name   |Example   |
|------|-------|-------|
|==   |``` Equal ```   |``` x == y ```   |
|!=   |``` Not Equal ```   |``` x != y ```   |
|>   |``` Greater than ```   |``` x > y ```   |
|<   |``` Less than ```   |``` x < y ```   |
|>=   |``` Greater than or equal ```   |``` x >= y ```   |
|<=   |``` Less than or equal ```   |``` x <= y ```   |
### Logical
|Operator   |Name   |Example   |Description
|-----|-----|-------|-------|
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
If you want to solve fast squares and square roots shift operators are very useful

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
To create a methode it needs to be created within a class. The class defines the visibility. Defining a method needs 3 main components:
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
public class ClassName {  //Class code is placed inside the curled braces
  //instances variables which hold the state for an object and should normally be private or protected
  private int classInt;
  private String classString;
  //constructor for object-orientation always public
  //There are many possibilities to define constructors, and you could handle different object calls
  public ClassName(int inputInt, String inputString) {
    classInt = inputInt;
    classString = inputString;
    //if the instance variable names and the method parameter have the same name: the object variable needs the this. operator
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
To handle exceptions in Java, you use try-catch blocks. A try block contains the code that might throw an exception, while a catch block contains the code that handles the exception. Multiple catch blocks can be chained together to handle different types of exceptions. You can also include a final block that contains code that should be executed whether an exception is thrown.
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
public class MyClass {
    public int add(int x, int y) {
        return x + y;
    }
    public double add(double x, double y) {
        return x + y;
    }
}
```
In this example, the add method is overloaded to accept both int and double parameters.
### Abstraction/ Interfaces
This is the process of hiding implementation details and exposing only the essential features of an object. In Java, this can be achieved through abstract classes and interfaces.
```Java
public interface Shape {
    void draw();
}
public class Circle implements Shape {

    @Override
    public void draw() {
        System.out.println("Drawing a circle");
    }
}
public class Rectangle implements Shape {

    @Override
    public void draw() {
        System.out.println("Drawing a rectangle");
    }
}
```
In this example, the Circle and Rectangle classes implement the Shape interface, which allows them to be treated as Shape objects.
Abstracts are a little bit more complicated than interfaces, but both need to be implemented in the subclass
```Java
public abstract class Animal {
    private String name;

    public Animal(String name) {
        this.name = name;
    }
    public String getName() {
        return name;
    }

    public abstract void makeSound();
}

```
In this example, Animal is an abstract class that defines a constructor and a getter method for the name field. The makeSound() method is declared as abstract, which means that any subclass of Animal must provide its own implementation of this method. An abstract class cannot be instantiated, but it can be used as a superclass for other classes.
## Collections
### Examples of Collections
1. List: A List is an ordered collection of elements that can contain duplicate values. The main implementations of List interface are ArrayList, LinkedList, and Vector.
2. Set: A Set is a collection that contains unique elements, and does not allow duplicates. The main implementations of Set interface are HashSet, TreeSet, and LinkedHashSet.
3. Map: A Map is a collection of key-value pairs, where each key is unique and maps to a corresponding value. The main implementations of Map interface are HashMap, TreeMap, and LinkedHashMap.
4. Queue: A Queue is a collection that stores elements in a First-In-First-Out (FIFO) order. The main implementations of Queue interface are LinkedList, PriorityQueue, and ArrayDeque.
5. Deque: A Deque is a double-ended queue that allows adding or removing elements from both ends. The main implementations of Deque interface are ArrayDeque and LinkedList.
6. Stack: A Stack is a collection that stores elements in a Last-In-First-Out (LIFO) order. The main implementation of Stack interface is Stack class.
7. Vector: A Vector is similar to ArrayList, but it is synchronized, which means that multiple threads cannot access it at the same time.
8. Hashtable: A Hashtable is similar to HashMap, but it is synchronized, which means that multiple threads cannot access it at the same time.
It is important to choose the appropriate collection based on the specific requirements of your program.
### Interface Vector
```Java
//import
import java.util.Vector;
//Constructor
Vector(int initialCapacity);
Vector(int initialCapacity, int capacityIncrement);
//Inserting
addElement(Object o);
insertElementAt(Object o, int index);
//Access & Management
public Object elementAt (int index) throws ArrayIndexOutOfBoundException
public Object firstElement() throws NoSuchElementException
public lastElement() throws NoSuchElementException

remove(Object o);
public final boolean isEmpty()
public final int size()
```
The separation to Arrays are that Objects of the vector class could only save Objects of the class OBJECT.
### Iterators
Normally Array iteration needs indexing, because an Array knows the predecessor and the successor. ```for(int i = 0; i < arrayOfChar.length();i ++ {...}) ```
For Collections there is another solution: Iterator Objects. ```Iterator iter();```
Iterators always start at the first element and moves between elements. Some methods are 
```Java
boolean hasNext(); //Test of successor
E next(); //returns next element or throws NoSuchElementException
void remove(); //removes the last returned element
default void forEachRemaining(Consumer<? super E> action) //This method performs the given action for each remaining element until all elements have been processed or the action throws an exception.
// Consumer<? super E> action is explained later, but briefly Consumer is a functional interface which represents an operation that accepts a single argument of type E or because of the "? super E" any other super-type of E
```
#### Examples with for-loops
```Java
Vector <...> v = new Vector<...>();
//Standard for-loop
for(Iterator en = v.iterator(); en.hasNext();)
sum += (Integer) en.next() //Cast is necessary!
//more elegant for-loop
for(Object o : v) {
    sum += (Integer) o; //Cast is necessary!
}
//forEach
v.forEach(d -> d.touch()); //for every element method touch
```
Interface Iterable is dependent on Iterator but not vice versa.

### Stack
Last-In-First-Out-Principle (LIFO)
Stack is a bit outdated but is necessary in
Implementation ```java.util.Stack```
The constructor ```Stack()```
Insertion ```public Object push(Object item)```
Remove ```Object pop() throws EmptyStackException```
Peek(top element) ```Object peek() throws EmptyStackException ```
other methods are empty(), search(Object o);
```java
Stack<Integer> myStack = neew Stack <>();
myStack.push(10);
myStack.push(20);
myStack.push(30);

System.out.println(myStack.peek()); // prints 30
System.out.println(myStack.pop()); // prints 30
System.out.println(myStack.search(20)); // prints 2
System.out.println(myStack.empty()); // prints false
```

## Generics and Lambdas 

### Generics
Generics in Java allow you to create classes, interfaces, and methods that can work with any data type. This means that you can write code that is reusable and can work with different data types without having to rewrite the same code multiple times.

```java
public class Box<T> {
   private T contents;

   public void setContents(T contents) {
      this.contents = contents;
   }

   public T getContents() {
      return contents;
   }
}
```
In this example,  a class called Box that has a single instance variable contents of type T is defined. The T is a type parameter, which means it can represent any data type.
Create an instance of Box with any data type by specifying the data type in angle brackets like this:

```java
Box<Integer> integerBox = new Box<Integer>();
Box<String> stringBox = new Box<String>();
```
There is also a way to use generics with common method structures i.e. printArray
```java
public static <T> void printArray(T[] array) {
   for (T element : array) {
      System.out.println(element);
   }
}

Integer[] intArray = { 1, 2, 3, 4, 5 };
String[] stringArray = { "apple", "banana", "orange" };
printArray(intArray);
printArray(stringArray);
```
in this example the declaration of the ```printArray``` methode with generic array parameters ```T[] array``` and the return value of a generic ```<T>``` is done.

### Lambdas

Lambdas in Java are a shorthand way to write anonymous functions. An anonymous function is a function that doesn't have a name and can be passed as an argument to another function. Lambdas allow you to write shorter and more concise code by defining a function in place without the need to define a separate method.

```java
List<String> names = Arrays.asList("Alice", "Bob", "Charlie", "David");

names.forEach(name -> System.out.println(name));
```
In this example, we define a List of Strings called names that contains four names. We then call the forEach method on the names list, which takes a Lambda expression as an argument. The Lambda expression is defined as name -> System.out.println(name).

This Lambda expression is a shorthand way of defining a function that takes a single argument called name and prints it to the console. We don't need to define a separate method for this function; we can define it inline using the Lambda expression.

The forEach method iterates over each element in the names list and applies the Lambda expression to each element. In this case, the Lambda expression prints each name to the console.

There are different equally important methods in Java:
1. ```forEach```: This method is defined for collections and streams, and it applies a Lambda expression to each element in the collection or stream.
2. ```map```: This method is defined for collections and streams, and it applies a Lambda expression to each element in the collection or stream, and returns a new collection or stream with the results.
3. ```filter```: This method is defined for collections and streams, and it applies a Lambda expression to each element in the collection or stream, and returns a new collection or stream with only the elements that satisfy the condition specified in the Lambda expression.
4. ```reduce```: This method is defined for collections and streams, and it applies a Lambda expression to combine all the elements in the collection or stream into a single result.
5. ```sort```: This method is defined for collections and streams, and it sorts the elements in the collection or stream according to a comparison function specified in a Lambda expression.
6. ```anyMatch, allMatch, noneMatch```: These methods are defined for collections and streams, and they apply a Lambda expression to check if any, all, or none of the elements in the collection or stream satisfy a given condition.
7. ```flatMap```: This method is defined for streams, and it applies a Lambda expression to each element in the stream, which returns another stream. The flatMap method then merges all the resulting streams into a single stream.
8. ```collect```: This method is defined for streams, and it collects the elements in the stream into a collection or other data structure specified in a Lambda expression.
9. ```peek```: This method is defined for streams, and it applies a Lambda expression to each element in the stream, but it doesn't modify the stream. Instead, it allows you to perform some side effects, such as printing debugging information.
10. ```distinct```: This method is defined for collections and streams, and it returns a new collection or stream with only the distinct elements, based on a comparison function specified in a Lambda expression.
11. ```skip, limit```: These methods are defined for collections and streams, and they allow you to skip or limit the number of elements in the collection or stream, based on a given condition specified in a Lambda expression.
12. ```findFirst, findAny```: These methods are defined for collections and streams, and they return the first or any element in the collection or stream that satisfies a given condition specified in a Lambda expression.

These methods provide a wide range of functionality for working with Lambdas in Java, and they are commonly used in many different programming tasks. By learning and understanding these methods, you can become more proficient in using Lambdas in your Java code.

## I/O
I/O (input/output) in Java refers to the process of reading input from a source and writing output to a destination. The input and output can come from different sources, such as a file, network socket, keyboard, or screen. In Java, I/O is implemented through the java.io package, which provides classes and methods for reading and writing data.

One of the first I/O Classes is the infamous ```Scanner```-Class.
```java
Scanner scanner = new Scanner(System.in);
System.out.print("Enter your name: ");
String name = scanner.nextLine();
System.out.println("Hello, " + name + "!");
```
Typically, if I/O is the topic, it has something to do with reading or writing of a file or something similar.
There are 2 distinct ways which look similar:
```java
try {
    PrintWriter writer = new PrintWriter("output.txt", "UTF-8");
    writer.println("This is some output.");
    writer.close();
} catch (IOException e) {
    System.out.println("Error writing to file: " + e.getMessage());
}

try {
    BufferedReader reader = new BufferedReader(new FileReader("input.txt"));
    String line = null;
    while ((line = reader.readLine()) != null) {
        System.out.println(line);
    }
    reader.close();
} catch (IOException e) {
    System.out.println("Error reading file: " + e.getMessage());
}
```
In the first example, we use the PrintWriter class from the java.io package to write output to a file called "output.txt". We write a line of text to the file using the println() method, and then close the file using the close() method. We also catch any exceptions that might occur while writing to the file.
In the second example,we use the BufferedReader and FileReader classes from the java.io package to read input from a file called "input.txt". We read the file line by line using the readLine() method, and print each line to the console using the println() method. We also catch any exceptions that might occur while reading the file.

These are just a few examples of I/O in Java, but there are many other classes and methods available for reading and writing data in different formats and from different sources. Understanding I/O is an important part of Java programming, as it allows you to interact with external data sources and produce meaningful output for your applications.

## Typical Java Errors

1. NullPointerException: This error occurs when you try to access a null reference or variable.
```java
String s = null;
System.out.println(s.length()); // NullPointerException

//Solution

String s = null;
if (s != null) {
    System.out.println(s.length());
}

// OR

String s = null;
Objects.requireNonNull(s, "s must not be null");
System.out.println(s.length());
```
2. ArrayIndexOutOfBoundsException: This error occurs when you try to access an array element that does not exist.
```java
int[] arr = new int[5];
System.out.println(arr[5]); // ArrayIndexOutOfBoundsException

//Solution

int[] arr = new int[5];
if (arr.length > 5) {
    System.out.println(arr[5]);
}

// OR

int[] arr = new int[5];
for (int i = 0; i < arr.length; i++) {
    System.out.println(arr[i]);
}
```
3. ClassCastException: This error occurs when you try to cast an object to a class that it is not an instance of.
```java
Object obj = new Integer(10);
String s = (String) obj; // ClassCastException

//Solution

Object obj = new Integer(10);
if (obj instanceof String) {
    String s = (String) obj;
    System.out.println(s);
}
```
4. ArithmeticException: This error occurs when you try to divide by zero or perform some other illegal arithmetic operation.
```java
int a = 10;
int b = 0;
int c = a / b; // ArithmeticException

//Solution

int a = 10;
int b = 0;
if (b != 0) {
    int c = a / b;
    System.out.println(c);
}

// OR

int a = 10;
int b = 0;
try {
    int c = a / b;
    System.out.println(c);
} catch (ArithmeticException e) {
    System.out.println("Illegal arithmetic operation");
}
```
5. FileNotFoundException: This error occurs when you try to access a file that does not exist.
```java
File file = new File("file.txt");
Scanner scanner = new Scanner(file); // FileNotFoundException

//Solution

File file = new File("file.txt");
if (file.exists()) {
    Scanner scanner = new Scanner(file);
    System.out.println(scanner.nextLine());
}

// OR

File file = new File("file.txt");
try {
    Scanner scanner = new Scanner(file);
    System.out.println(scanner.nextLine());
} catch (FileNotFoundException e) {
    System.out.println("File not found: " + file.getName());
}
```
These are just a few examples of common Java errors and their solutions, but there are many other errors that can occur in Java programming. By understanding how to identify and solve these errors, you can become a more proficient Java developer and write more robust and error-free code.
These are the ones which occurred in my code, and I'm going to update it regularly

Enes Sabi - 13.15.2023
