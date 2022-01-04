# Overview
- [Basic Syntax](#basic-syntax)
- [Length Methods](#length-methods)
- [For Loops](#for-loops)
- [Conditional Statements and While Loops](#conditional-statements-and-while-loops)
- [Helper Method Declaration](#helper-method-declaration)
- [Boolean and Arithmetic Operators](#boolean-and-arithmetic-operators)
- [Commenting and Printing Code](#commenting-and-printing-code)
- [Accessing Characters in a String](#accessing-characters-in-a-string)
- [Accessing the Last Element in a List](#accessing-the-last-element-in-a-list)

## Basic Syntax

Python is dynamically typed, meaning that data types are determined upon runtime, so variable types do not need to be declared when writing a program:

```python
word = "apple"
number = 5
list = [1, 2, 3]
```

Java, however, is statically typed, meaning that you will need to declare the variable type the first time you use it but not necessarily in the future:

```java
String word = "apple";
int number = 5;
int[] list = new int[] {1, 2, 3};
number += 5;
```
Also make note of the fact that Java requires a semicolon at the end of each line.

## Length Methods

In Python, there is a useful `len()` method that can be used to find the length/size of many different data structures:

```python
word = "apple"
list = [1, 2, 3]
wordLength = len(apple)
listLength = len(list)
```
In Java, an array uses the `.length` method, a String object uses `.length()`, and  Collections - `List`, `Set`, `Map`, etc. (if you don't know these, you'll learn them soon!) - use the `.size()` method.

```java
String word = "apple";
int[] list = new int[] {1, 2, 3};
ArrayList<String> list2 = new ArrayList<>();
int wordLength = word.length();
int listLength = list.length;
int list2length = list.size();
```

## For Loops

The Python for loop is very simple:

```python
sum = 0
list = [1, 2, 3]
for i in range(len(list)):
    sum += list[i]
```

In Java, you will need to define your index that travels through the loop and explicitly increment it. You'll also need to surround your constraints with parentheses, and the body of the for loop needs to be stored in curly brackets:

```java
int sum = 0;
int[] list = new int[] {1, 2, 3};
for (int i = 0; i < list.length; i++) { 
    sum += list[i];
}
```

If you would like to move through the loop by more than increments of 1, the following describes both processes in Python and Java:

```python
#increment by 2
for i in range(0, len(list), 2):
    doStuff()

#move from back to front
for i in range(len(list) - 1, -1, -1):
    doStuff()
```
```java
//increment by 2
for (int i = 0; i < list.length; i+= 2) {
    doStuff();
}
 
//move from back to front
for (int i = list.length - 1; i >= 0; i--) {
    doStuff();
}
```

## Conditional Statements and While Loops

The major difference between Python and Java for conditional statements and while loops is the colon/bracket syntax. Python enacts the above statements with colons, and Java encloses the body of statements in curly brackets and surrounds each condition with parentheses.

### Conditional Statements

```python
list = [1, 2, 3]
for i in range(len(list)):
    if list[i] == 1:
        print("First!")
    else if list[i] == 2:
        print("Second!")
    else:
        print("Third!)
```      
```java
int[] list = new int[] {1, 2, 3};
for (int i = 0; i < list.length; i++) { 
    if (list[i] == 1) {
        System.out.println("First!");
    }
    else if (list[i] == 2) {
        System.out.println("Second!");    
    }
    else {
        System.out.println("Third!");
    }
```

### While Loops

```python
while something:
    doStuff()
```
```java 
while (something) {
    doStuff();
}
```

## Helper Method Declaration

Python has a unique feature where helper methods can be declared in the middle of a method:

```python
class CirclesCountry:
    def leastBorders(x, y, r, x1, y1, x2, y2):
        crosses = 0
        def isInside(x, y, cx, cy, r):
            dist = (x-cx)*(x-cx) + (y-cy)*(y-cy)
            radSquared = r*r
            return dist < radSquared
        #do stuff using isInside()
        return crosses
```

Java requires the helper method to be declared outside of the method and within the class:

```java
public class CirclesCountry {
    public int leastBorders(int[] x, int[] y, int[] r,
                            int x1, int y1, int x2, int y2) {
        int crosses = 0;       
        //solve the problem using isInside()
        return crosses;
    }
    public boolean isInside(int x, int y, int cx, int cy, int r){
        double dist = (x-cx)*(x-cx) + (y-cy)*(y-cy);
        double radSquared = r*r;
        return dist < radSquared;
    }
}
```

## Boolean and Arithmetic Operators

For statements involving booleans, Python simply uses English words to represent "and" and "or" in code:

```python
if someCondition and anotherCondition:
    continue
else if thisCondition or thatCondition:
    print("something")
```

On the other hand, Java makes use of the boolean operators `&&` and `||` instead of `and` and `or` respectively:

```java
if (someCondition && anotherCondition) {
    continue;
}
else if (thisCondition || thatCondition) {
    System.out.println("something");
}
```
Boolean operators like `<`, `>`, `<=`, and `>=` are identical for both languages. Similarly, addition, subtraction, multiplication, and the modulo operator are the same (`+`, `-`, `*`, `%`). Division and exponentiation, however, are different. Python float divides numbers with `/`, integer divides with `//`, and exponentiates numbers with `**`:

```python
x = 3
y = 2

num1 = x / y
num2 = x // y
squared = x**y

'''
num1 = 1.5
num2 = 1
squared = 9
'''
```

Java only uses a single division operator `/`, and the result depends on the data types of the dividend and the divisor. For example, division with 2 `double` values returns a double, and division with integers returns an integer. Additionally, Java exponeniates using the `Math.pow(double a, double b)` method:

```java
int x = 3;
int y = 2;
double x1 = 3.0;
int y = 2.0;


int num1 = x / y;
int num2 = x1 / y1;
int squared = Math.pow(x, y);

/*
num1 = 1
num2 = 1.5
squared = 9
*/
```

## Commenting and Printing Code

Both languages have support for single and multiline comments:

```python
#Python uses # for one line commments

'''
And it uses this 
for multiline comments
'''
```
```java 
//java uses // for one line comments

/*
And it uses that
for multiline comments
*/
```
The process for printing in Java can be a bit more involved than in Python. Python does not require a main method to print, but it can still print with one. For example, either code snippet below will print "Hello world"

```python
print("Hello world")
```

```python
def simpleFunc():
    print("Hello world")

if __name__ == "__main__":
    simpleFunc()
```

Unless one is using JShell, a main method will be required to print in Java. Notice that each language has its own idiomatic way of creating a main method, and Java requires an instance of the class to be created so that its methods can be called.

```java
public class Example {

public void simpleFunc() {
    System.out.println("Hello world");
}

public static void main(String[] args) {
    Example ex = new Example();
    ex.simpleFunc();
}
}
```

## Accessing Characters in a String

Python nearly treats `String` objects as arrays, meaning that you can accessing each character by its index:

```python
word = "Python"
p = word[0]
y = word[1]
``` 

On the other hand, Java leverages the `.charAt(int index)` method to access individual characters:

```java
String word = "Java";
char j = word.charAt(0);
char a = word.charAt(1);
```

## Accessing the Last Element in a List

Python has some really neat syntax for accessing the last element in a list:
```python
list[-1]
```
In Java, that would throw an `IndexOutOfBoundsException`. Instead, try using this:
```java
int[] list = new int[] {1, 2, 3};
int last = list[list.length-1];
```


<br />
<br />
<br />
<br />



Written by Matthew Giglio, E'23
