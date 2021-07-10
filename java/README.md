# java

----
- [jshell (java shell tool) - interactive REPL tool](#jshell-java-shell-tool---interactive-repl-tool)
- [getting started](#getting-started)
- [resources](#resources)
----

## jshell (java shell tool) - interactive REPL tool
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

## resources
- [JShell](https://docs.oracle.com/javase/9/jshell/introduction-jshell.htm#JSHEL-GUID-630F27C8-1195-4989-9F6B-2C51D46F52C8)