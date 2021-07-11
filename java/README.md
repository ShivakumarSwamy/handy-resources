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

## resources
- [JShell](https://docs.oracle.com/javase/9/jshell/introduction-jshell.htm#JSHEL-GUID-630F27C8-1195-4989-9F6B-2C51D46F52C8)
- [Statement](https://www.programiz.com/java-programming/expressions-statements-blocks)
- [Udacity Fundamentals Glossary](https://video.udacity-data.com/topher/2021/January/5fef31c7_jpnd-c1-java-fundamentals-glossary/jpnd-c1-java-fundamentals-glossary.pdf)

## terms
- statement: a complete unit of execution
- primitive type: a value with no additional data 
- function: reusable block of code