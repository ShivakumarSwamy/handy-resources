# java

----
- [jshell (java shell tool) - interactive REPL(read-eval-print-loop) tool](#jshell-java-shell-tool---interactive-replread-eval-print-loop-tool)
- [getting started](#getting-started)
- [source code, byte code and machine code](#source-code-byte-code-and-machine-code)
- [assignment statement, static typing](#assignment-statement-static-typing)
- [primitive types](#primitive-types)
- [reference types](#reference-types)
- [type casting](#type-casting)
- [truncation](#truncation)
- [method](#method)
- [stack and heap memory](#stack-and-heap-memory)
- [loops](#loops)
  * [while](#while)
  * [for](#for)
  * [do while](#do-while)
- [javadoc](#javadoc)
- [class, object and variables](#class-object-and-variables)
  * [defining a class](#defining-a-class)
- [garbage collection](#garbage-collection)
- [package, inheritance, interface, polymorphism, abstract class](#package-inheritance-interface-polymorphism-abstract-class)
- [error, exception](#error-exception)
- [enum](#enum)
- [resources](#resources)
- [terms](#terms)
----

## jshell (java shell tool) - interactive REPL(read-eval-print-loop) tool
Requires java 9 and above
```shell
jshell
```

## getting started
simple java class(file name: GettingStarted.java)
```java
public class GettingStarted {
    public static void main(String[] args) {
        // single line comment, main method is entrypoint
        System.out.println("Hello World");
    }
}
```

```shell
# compile the code
javac GettingStarted.java

# run 
java GettingStarted.java
```

## source code, byte code and machine code
```text
             compile             java virtual machine
source code ---------> bytecode ----------------------> machine code
```

## assignment statement, static typing
```text
                            static typing
|-----------------------------------------------------------------------|
|                               |-- statement ends with semicolon       |
|                   int age = 42; // assignment statement               |
|                    |   |  |-- assignment operator                     |
|        data type --|   |-- variable name                              |                                    |
|-----------------------------------------------------------------------|
```

## primitive types
- Has memory size location

Data Type|Size
---------|-------
byte     | 1 byte
short    | 2 bytes
int      | 4 bytes
long     | 8 bytes
float    | 4 bytes
double   | 8 bytes
boolean  | 1 byte
char     | 2 bytes

## reference types
- reference to a data object
- additional data and behaviour
- do not have a specific memory allocation size

## type casting
- 2 types 
  - automatic(smaller data type to larger data type)
  - manual(larger data type to smaller data type, one reference type into another reference type)

## truncation
- loss of precision during manual type casting
```text
## example
double doubleNumber = 3.5;
int intNumber = (int) doubleNumber;
System.out.println(intNumber);

## output (truncating additional data, not rounding off, in this case we lose precision)
3
```

## method
- reusable block of code which is associated with a class or object
```text
access          |-- return type
modifier --|    |     |-- method name             |-- method parameter
        public double sum(int leftOperand, int rightOperand) {
            return leftOperand + rightOperand; -- return statement
        }

sum(1, 2); // invoking or calling a method
```

## stack and heap memory
- stack (last-in-first-out) and heap are two different memory regions of java
  
- stack used for primitives and object references
- heap to store object itself
  
- items in stack stay until the method is running
- items in heap stay until object reference is not their anymore or application exits

```text
// A rough overview of memory region and code co-relation 
                                             |---------------------------------------------------------|
                                             |                        Memory                           |
public static void main(String[] args) {     ||--------------------------------|  |-------------------||
    int j = 23;                              ||            Stack               |  |       Heap        ||
    Object object = new Object();            || Object object -> Object@1341 --|--|----> Id:1341      ||
                                             ||                                |         Type:Object  ||
}                                            || int j = 23                     |  |                   || 
                                             ||                                |  |                   ||
                                             || main                           |  |                   ||
                                             ||--------------------------------|  |-------------------||
                                             |                                                         |
                                             |---------------------------------------------------------|
```

## loops

### while
```text
while(condition) {
    execution block;
}
```

### for
```text
for(initialization; condition; increment or decrement after execution block runs) {
    execution block;
}
```

### do while
```text
do {
    execution block;
} while(condition);
```

## javadoc
```java
/**
 * The place to write description
 * 
 * below are called block tags
 * @author author block tag
 * @see see block tag
 */
```

## class, object and variables
- class acts as a template for an object
- object is a data structure encapsulating the following 
  * state = variables
  * behaviour = methods

### defining a class
```text
 |--> access modifier
 |      |--> class keyword, denoting this is a java class 
 |      |        |--> Class name 
public class UpperCamelCaseClassName { ---> start with open flower bracket
    
    public static final String CLASS_VARIABLE = "CONSTANT_VALUE"; ---> associated with class, which is same for all objects
    
    private int instanceVariable; ---> associated with objects, allowing each object to have own state
    
    public UpperCamelCaseClassName() {} ---> constructor used to initialize the object, same as class name
    
    
    public void setInstanceVariable(int aInstanceVariableValue) { --> Mutator method, 
        instanceVariable = aInstanceVariableValue;                    which allows to change the values of variables
    }
    
    public int getInstanceVariable() { --> Accessor method, 
        return instanceVariable;           which allows to access variables
    }
   
} ---> ends with closed flower bracket
```

## garbage collection
- searches heap memory, to remove objects that do not have references 

## package, inheritance, interface, polymorphism, abstract class

- package: organize the code, similar to namespaces
- inheritance: a class inherits all state and behavior of a parent(super) class  
- interface: acts a contract, and decouple functions
- polymorphism: many forms an object can take
- abstract class: sub-class can benefit from the common implementation or either override it.  

```text
package test.one; // package

interface Owner {} // interface

class abstract Vehicle implements Owner {} // abstract class

class Car extend Vehicle {} // inheritance 

class Boat extend Vehicle {} // boat is exhibiting polymorphism as it can take three forms Owner, Vehicle, and Boat
```

## error, exception

- Error: unrecoverable error for application
- Exception: recoverable error for application
  - Checked: the calling method can recover from exception
  - UnChecked/Runtime: the calling method cannot recover from exception
```text
                    +-----------+
                    | Throwable |
                    +-----------+                                       +-------------+
          |---------------||------------------|                 |-------|   Checked   | 
          |                                   |                 |       +-------------+
    +-----------+                     +---------------+         |
    |   Error   |                     |   Exception   |---------|
    +-----------+                     +---------------+         |       +-------------+
                                                                |-------|  Unchecked  |
                                                                        +-------------+
```

## enum

- an enumerated list of constants

```text
 |--------------- enum keyword
enum Choice {
    YES,  --- constant
    NO
}
```

## resources
- [jshell](https://docs.oracle.com/javase/9/jshell/introduction-jshell.htm#JSHEL-GUID-630F27C8-1195-4989-9F6B-2C51D46F52C8)
- [statement](https://www.programiz.com/java-programming/expressions-statements-blocks)
- [udacity java fundamentals glossary](https://video.udacity-data.com/topher/2021/January/5fef31c7_jpnd-c1-java-fundamentals-glossary/jpnd-c1-java-fundamentals-glossary.pdf)

## terms
- statement: a complete unit of execution
- primitive type: a value with no additional data 
- function: reusable block of code