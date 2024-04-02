I. OOP
-------
- **OOP** stands for Object-Oriented Programming.
- **OOP** is a programming paradigm that uses "objects" to design applications and computer programs.
- Properties:
    - **Encapsulation** (tính đóng gói): 
           
        - Encapsulation is the mechanism that binds together code and the data it manipulates, and keeps both safe from outside interference and misuse.
            
        - **In Java** this achieved by using access specifiers such as **public, private, protected and default**.
    - **Inheritance** (tính kế thừa): 
        - Inheritance is a mechanism wherein a new class is derived from an existing class.
        - **In Java**, classes can inherit attributes and methods from another class.
        - Note: Super được sử dụng để tham chiếu trực tiếp đến biến instance của lớp cha, ví dụ:

        ```java
        class Animal {
            void eat() {
                System.out.println("eating...");
            }
        }
        class Dog extends Animal {
            void bark() {
                System.out.println("barking...");
            }
            void work() {
                super.eat();
                bark();
            }
        }
        -> Ouput: eating...
                  barking...
        ```
    - **Polymorphism**(tính đa hình): 
        - Polymorphism is the ability of a programming language to present the same interface for several different underlying data types.
        - **In Java**, this is achieved by method overloading and method overriding.
            - Overloading (nạp chồng): 
                - Overloading is the ability to define more than one method with the same name in a class.
                - The methods must have different method parameters/ tham số.
                - EX:

                    ```java
                    class A{
                        void sum(int a,int b){
                            System.out.println(a+b);
                        }
                        void sum(int a,int b,int c){
                            System.out.println(a+b+c);
                        }
            - Overriding (ghi đè):
                - Overriding means having two methods with the same method name and parameters.
                - One of the methods is in the parent class and the other is in the child class.
                - Note: connot override static,final, private methods.
                - Ex:
                    Same method "eat" of Animal, cow eats grass but lion eat meat.
    - **Asbtraction** (tính trừu tượng):
        - compare abstract class vs interface:
            - Abstract class:
                - Is a class that contains abstract method
                - Abstract methods dont have body
                - Other classes inheriting abstract class need to re-define abstract method
                - Cannot extends multiple abstract class
                - 2 types of method : abstract-empty method and non-abstract( normal method) - executable method
                - java not support multiple inheritance 
                - Method of abstract class can be static, final, private, protected, public but only public and protected for other classes to inheritate
                
                -> use abstract class when group of objects inheritate from the same class. 
            - Interface:
                - is a template, not object class
                - all methods are abstract
                - use keyword "implements" to inheritate interface
                - methods like abstract class (dont have body)
                - multiple inheritance
                - cannot initialize object
                - all methods are abstract
                - all methods are public
                - one class can inherit multiple interface
                
                -> use interface when group of objects have same behavior.
        How is a constructor invoked in Java?


II. Java Core
------------
1. Primitive data type
- Note :

    - The default type for floating-point literals in Java is double, which provides higher precision compared to the float type
    - The BigDecimal data type in Java is used to represent floating-point numbers with higher precision, making it suitable for financial and decimal-based calculations.
2. Conditional statements
- Note: Ternanry Operator
    - The ternary operator is a shorthand version of an if-else statement.
    - Syntax: condition ? expression1 : expression2
    - If the condition is true, the ternary operator returns expression1; otherwise, it returns expression2.
    - Ex: int result = (a > b) ? a : b;
3. Loops
4. Reference data type
- provide a mechanism to work with objects by holding their memory addresses.
- When assigning one reference variable to another in Java, only the reference (memory address) is copied, not the entire referenced object. Both variables will refer to the same object in memory.
5. String
- String Literal vs. String Object
    - String Literal:
        - A string literal is a sequence of characters enclosed in double quotes (chỉ định sẵn)
        - String literals are stored in the string pool.
        - String literals are immutable( can only get but not set())
    - String Object:
        - A string object is an instance of the String class.
        - String objects are stored in the heap memory.
        - String objects are mutable.
- Compare StringBuilder vs StringBuffer
    - StringBuilder:
        - StringBuilder is non-synchronized, which means it is not thread-safe.
        - StringBuilder is faster than StringBuffer because it is not thread-safe.
        - StringBuilder is used in a single-threaded environment.
    - StringBuffer:
        - StringBuffer is synchronized, which means it is thread-safe.
        - StringBuffer is slower than StringBuilder because it is thread-safe.
        - StringBuffer is used in a multi-threaded environment.
        * thread-safe: (Nếu một object được tạo ra và chỉ được sử dụng bên trong method tạo ra nó, thì nó được coi là thread safe)
6. Java Date and Time
- Java 8 introduced the java.time package, which contains classes to represent date and time.
- Java 9 and later versions introduced the java.time.chrono package, which contains classes to represent the calendar system.
7. Wrapper class
- Note: When you create a Wrapper object using valueOf(), the JVM will check if there is already a Wrapper object with the same value in memory. If there is, the valueOf() method will return that object. If there is no Wrapper object with the same value in memory, the valueOf() method will create a new object and return that object.
8. Array
- Note : A variable arguments list, also known as varargs, is a special type of parameter that can be used to pass a variable number of arguments to a function. The variable arguments list is always the last parameter in the list of arguments.
- variable argument method: 
    - Syntax: returnType methodName(dataType... variableName)
    - Ex: public static int sum(int... numbers)

9. Collection

    a. List
    - List is an interface that extends the Collection interface.
    - Note: Vector vs ArrayList vs LinkedList:
        - Vector:
            - Vector is synchronized, which means it is thread-safe.
            - Vector is slower than ArrayList because it is thread-safe.
            - Vector is used in a multi-threaded environment.
        - ArrayList:
            - ArrayList is non-synchronized, which means it is not thread-safe.
            - ArrayList is faster than Vector because it is not thread-safe.
            - ArrayList is used in a single-threaded environment.
        - LinkedList:
            - LinkedList is a doubly-linked list implementation of the List interface.
            - LinkedList is faster than ArrayList when adding or removing elements from the list.
            - LinkedList is slower than ArrayList when accessing elements by index.


    b. Set
    - HashSet:
        - HashSet does not maintain the insertion order of elements.
        - HashSet does not allow duplicate elements.
        - HashSet allows only one null element.
    - LinkedHashSet:
        - LinkedHashSet maintains the insertion order of elements.
        - LinkedHashSet does not allow duplicate elements.
        - LinkedHashSet allows only one null element.
    - TreeSet:
        - TreeSet stores elements in ascending order.
        - TreeSet does not allow null elements.
    - Note : For two objects to be considered equal and treated as duplicates by a Set implementation, the `equals()` method needs to return `true`, indicating that the objects have the same state and are considered equal.
    
    c. Map   
        -HashMap:
            - HashMap does not maintain the insertion order of elements.
            - HashMap allows only one null key but multiple null values.
       
        -HashTable: (thread-safe synchronized version of HashMap)
            - HashTable is synchronized, which means it is thread-safe.
            - HashTable does not allow null keys or values.
            - HashTable is slower than HashMap because it is thread-safe.
            - HashTable is used in a multi-threaded environment. 
         - LinkedHashMap:
            - LinkedHashMap maintains the insertion order of elements.
            - LinkedHashMap allows only one null key but multiple null values.
        - TreeMap:
            - TreeMap stores elements in ascending order of keys.
            - TreeMap does not allow null keys but allows multiple null values.
    10. Generics
    - Generics in Java allow you to create classes, interfaces, and methods that operate on objects of specified types.
    - Example : generic in ArrayList
        ![Example](https://codelearnstorage.s3.amazonaws.com/Media/Default/Users/SeiSilver/GenericImg/2-1.png)
    - Note:
        - The diamond operator (<>) is used to specify the type of the generic class.
        - Generic classes can have multiple type parameters.
        - The type parameter can be a class or an interface.


III. Functional programming
---------------------------
* Overview:
    - No state
    - No side effects (pure functions)
    - Immutable variables
    - recursion instead of loops
    - Higher-order functions (functions as parameters and return functions). Ex:

            public class HigherOrderFunctionClass {
                public <T> IFactory<T> createFactory(IProducer<T> producer, IConfigurator<T> configurator) {
                    return () -> {
                    T instance = producer.produce();
                    configurator.configure(instance);
                    return instance;
                    }
                }
            }
    

    - Funtional Interfaces: là interface chỉ có 1 method abstract
    - Note: 
        - A lambda expression is a concise way to represent an anonymous function.
        - A lambda expression can have zero or more parameters.
    
IV. Thread and Multiple Thread
-------------------------------
1. Thread
- Methods:
    - The start() method is used to start a thread.
    - The run() method contains the code that will be executed by the thread.
    - The join() method is used to wait for a thread to finish its execution.
    - The sleep() method is used to pause the execution of a thread for a specified amount of time.
- life time of thread:
    - New: The thread is in the new state before the start() method is called.
    - Runnable: The thread is in the runnable state after the start() method is called.
    - Running: The thread is in the running state when the run() method is executing.
    - Blocked: The thread is in the blocked state when it is waiting for a resource.
    - Terminated: The thread is in the dead state when the run() method has finished executing.
- How to implement thread:
    - By extending the Thread class:

            public class ThreadDemo extends Thread {
            private Thread t;
            private String threadName;
        
            ThreadDemo(String name) {
                threadName = name;
                System.out.println("Creating " + threadName);
            }
        
            @Override
            public void run() {
                System.out.println("Running " + threadName);
                try {
                    for (int i = 4; i > 0; i--) {
                        System.out.println("Thread: " + threadName + ", " + i);
                        // Let the thread sleep for a while.
                        Thread.sleep(50);
                    }
                } catch (InterruptedException e) {
                    System.out.println("Thread " + threadName + " interrupted.");
                }
                System.out.println("Thread " + threadName + " exiting.");
            }
        
            public void start() {
                System.out.println("Starting " + threadName);
                if (t == null) {
                    t = new Thread(this, threadName);
                    t.start();
                }
            }
        
        }

        Running program:

                public class ThreadDemoTest {
                    public static void main(String args[]) {
                        System.out.println("Main thread running... ");
                
                        ThreadDemo T1 = new ThreadDemo("Thread-1-HR-Database");
                        T1.start();
                
                        ThreadDemo T2 = new ThreadDemo("Thread-2-Send-Email");
                        T2.start();
                
                        System.out.println("==&gt; Main thread stopped!!! ");
                    }
                }

        -> Working flow:
        ![flow](https://gpcoder.com/wp-content/uploads/2018/02/Multi-Thread-Flow.png)
    - By implementing the Runnable interface:

            class RunnableDemo implements Runnable {
            private Thread t;
            private String threadName;
        
            RunnableDemo(String name) {
                threadName = name;
                System.out.println("Creating " + threadName);
            }
        
            @Override
            public void run() {
                System.out.println("Running " + threadName);
                try {
                    for (int i = 4; i > 0; i--) {
                        System.out.println("Thread: " + threadName + ", " + i);
                        // Let the thread sleep for a while.
                        Thread.sleep(50);
                    }
                } catch (InterruptedException e) {
                    System.out.println("Thread " + threadName + " interrupted.");
                }
                System.out.println("Thread " + threadName + " exiting.");
            }
        
            public void start() {
                System.out.println("Starting " + threadName);
                if (t == null) {
                    t = new Thread(this, threadName);
                    t.start();
                }
            }
        
}

2. Multiple Thread
- Note:
    + The range of thread priorities in Java is from 1 to 10.
    + The default priority assigned to a thread in Java is 5. The Thread class defines NORM_PRIORITY as the default priority value.






Refference:
1. https://jenkov.com/
2. Udemy course: Java Programming for Complete Beginners
3. [Javapoint.com](https://www.javatpoint.com/)