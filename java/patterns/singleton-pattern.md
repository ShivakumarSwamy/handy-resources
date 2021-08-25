# singleton pattern

----
- [description](#description)
- [examples](#examples)
    * [lazy initialization, not thread safe](#lazy-initialization-not-thread-safe)
    * [lazy initialization, thread safe, synchronized method](#lazy-initialization-thread-safe-synchronized-method)
    * [lazy initialization, thread safe, synchronized statement, double check locking (not preferred)](#lazy-initialization-thread-safe-synchronized-statement-double-check-locking-not-preferred)
    * [lazy initialization, thread safe, without synchronization, initialization-on-demand holder](#lazy-initialization-thread-safe-without-synchronization-initialization-on-demand-holder)
    * [eager initialization, thread safe](#eager-initialization-thread-safe)
- [use cases](#use-cases)
- [resources](#resources)
----

## description

- Allows only one object instantiation of a class

## examples

### lazy initialization, not thread safe
```java
public class LazyInitializationSingleton {
    
    private static LazyInitializationSingleton lazyInitializationSingleton;
    
    private LazyInitializationSingleton() {}
    
    public static LazyInitializationSingleton getInstance() {
        if (lazyInitializationSingleton == null) {
            lazyInitializationSingleton = new LazyInitializationSingleton();
        }
        return lazyInitializationSingleton;
    }
}
```

### lazy initialization, thread safe, synchronized method
```java
public class LazyInitializationSingleton {
    
    private static LazyInitializationSingleton lazyInitializationSingleton;
    
    private LazyInitializationSingleton() {}
    
    public static synchronized LazyInitializationSingleton getInstance() {
        if (lazyInitializationSingleton == null) {
            lazyInitializationSingleton = new LazyInitializationSingleton();
        }
        return lazyInitializationSingleton;
    }
}
```

### lazy initialization, thread safe, synchronized statement, double check locking (not preferred)
```java
public class LazyInitializationSingleton {

    private static LazyInitializationSingleton lazyInitializationSingleton;

    private LazyInitializationSingleton() {}

    public static synchronized LazyInitializationSingleton getInstance() {
        if (lazyInitializationSingleton == null) {
            synchronized (LazyInitializationSingleton.class) {
                if (lazyInitializationSingleton == null) {
                    lazyInitializationSingleton = new LazyInitializationSingleton();
                }
            }
        }
        return lazyInitializationSingleton;
    }
}
```

### lazy initialization, thread safe, without synchronization, initialization-on-demand holder
```java
public class LazyInitializationSingleton {

    private LazyInitializationSingletonHolder(){}
    
    private static class LazyInitializationSingletonHolder {
        static final LazyInitializationSingleton INSTANCE = new LazyInitializationSingleton();
    }
    
    public static LazyInitializationSingleton getInstance() {
        return LazyInitializationSingletonHolder.INSTANCE;
    }
}
```

### eager initialization, thread safe
```java
public class LazyInitializationSingleton {
    
    private static final LazyInitializationSingleton LAZY_INITIALIZATION_SINGLETON 
            = new LazyInitializationSingleton();
    
    private LazyInitializationSingleton() {}
    
    public static LazyInitializationSingleton getInstance() {
        return lazyInitializationSingleton;
    }
}
```

## use cases
- when an object needs to be shared for the whole application - global state


## resources
- [double checked locking](https://en.wikipedia.org/wiki/Double-checked_locking)
- [javatpoint singleton pattern](https://www.javatpoint.com/singleton-design-pattern-in-java)
- [tutorialspoint singleton pattern](https://www.tutorialspoint.com/design_pattern/singleton_pattern.htm)
- [singleton design pattern in java and spring](https://azeynalli1990.medium.com/singleton-design-pattern-in-java-and-in-spring-9fe3eb007af1)
- [initialization-on-demand holder idiom](https://en.wikipedia.org/wiki/Initialization-on-demand_holder_idiom)