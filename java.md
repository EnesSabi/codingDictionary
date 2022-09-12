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
### Arithmetic operators