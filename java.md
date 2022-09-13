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
If you want to solve fast squares and squareroots shiftoperators are very useful
