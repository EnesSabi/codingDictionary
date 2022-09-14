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