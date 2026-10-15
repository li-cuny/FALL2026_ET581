
# 1. Constructor chaining
```java
class Student {
    String name;
    int age;

    Student() {
        this("Unknown", 0); // Call another constructor
    }

    Student(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public static void main(String[] args) {
        Student s1 = new Student();
        Student s2 = new Student("Alice", 20);

        System.out.println(s1.name + ", " + s1.age);
        System.out.println(s2.name + ", " + s2.age);
    }
}
```
- this() calls another constructor in the same class.
- this() must be the first statement in the constructor.
- this("Unknown", 0) calls the constructor with two parameters.

# 2. Named Object & Anonymous object

```java
String name = new String("Alice"); // named object
name.length(); 
new String("Bob").length(); // anonymous object
```

# 3. instance block & `static` block

## 3.1 Static Block

- Runs **only once** — when the class is loaded.
- Executed **before `main()`** or **before any object of the class is created**.
- **Cannot access instance variables** or use `this` — there is no object context.
- Can access **static variables** and call **static methods**.
- A class can have **multiple static blocks**, executed in the **order they appear**.

**Example:**
```java
class Car {
    static {
        System.out.println("Static block is invoked");
    }
    // only once when class loaed - class level
}
```

---

## 3.2 Instance Block

- An **instance block** (also called an **initializer block**) is a block of code inside a class **without the `static` keyword**.
- Runs **every time an object is created**, **before the constructor**.
- Can access **instance variables** directly.

**Example:**
```java
class Car {
    {
        System.out.println("Instance block is invoked");
    } // every time object created - obj level
}
```




# 4. Memory
```java
class Student {
    String name;
    int age;

    // Method stored in Method Area
    void display() {
        System.out.println("Name: " + name + ", Age: " + age);
    }
}

public class Main {
    public static void main(String[] args) {
        Student s1 = new Student();   // Object created in Heap
        s1.name = "Alice";            // Instance field in Heap
        s1.age = 20;                  // Instance field in Heap

        s1.display();                 // display() method called
    }
}
```
## 4.1 Method Area

* Stores **class bytecode** and **method code** (e.g., `display()`).  
* Shared by all `Student` objects.

```text
Method Area:
 └─ Class: Student
     └─ Method: display()
```
Key Idea:

* All Student objects share the same display() method in memory.

* Only one copy exists for the class.

## 4.2 Heap

Stores object instances and their instance fields.
```
Heap:
 └─ Object#1: Student (s1)
      ├─ name → "Alice"
      └─ age  → 20
```
Key Idea:

* Each Student object has its own copy of fields (name and age).

* Multiple objects will each have separate fields in the Heap.

## 4.3 Stack

Stores local variables and method call frames.
```
Stack:
 └─ main() frame
     ├─ local variable: s1 → reference to Object#1

 └─ display() frame (when s1.display() is called)
     ├─ hidden parameter: this → Object#1
```
Key Idea:

* Local variables like s1 store references to objects in Heap.

* When a method is called, a new frame is created on the stack with this pointing to the object.

## 4.4. Visual Summary
| Memory Area   | Stores                                     |
|---------------|-------------------------------------------|
| Method Area   | Class definitions & method code           |
| Heap          | Object instances & instance fields        |
| Stack         | Local variables & method call frames      |



# 5. Nested / Inner Classes

### **Purpose**
Group related classes to improve **readability** and **maintainability**.
* Static Nested Class — does not require an outer object to create its object.
* Non-static Inner Class — requires an outer object to create its object.

### 5.1 Static Nested Class
- Can be accessed **without creating** an outer class object.
```java
class Outer {
    int x = 10;         // instance variable
    static int y = 20;  // static variable

    static class StaticInner {
        void show(Outer outer) { // pass Outer instance to access x
            System.out.println("Outer x = " + outer.x); // instance variable
            System.out.println("Outer y = " + y);       // static variable
        }
    }
}

public class Main {
    public static void main(String[] args) {
        Outer outer = new Outer(); // instance of Outer
        Outer.StaticInner inner = new Outer.StaticInner(); // create static inner

        inner.show(outer); // print both x and y
    }
}
```

### 5.2  **Non-static Nested(Inner) Class**
```java
class Outer {
    int x = 10;

    class Inner {
        void show() {
            System.out.println("Outer x = " + x);
        }
    }
}
```
```java
Outer o = new Outer();
Outer.Inner i = o.new Inner();
i.show();  // Outer x = 10
```

---


#### 5.3 private class 
- Not accessible from outside the outer class.
```java
class Library {
    private String name;

    // Private inner class
    private class Staff {
        private String staffName;

        Staff(String staffName) {
            this.staffName = staffName;
        }

        void display() {
            System.out.println("Staff Name: " + staffName + ", Library: " + name);
        }
    }

    Library(String name) {
        this.name = name;
    }

    // Method inside outer class can access private inner class
    void showStaff(String staffName) {
        Staff s = new Staff(staffName);
        s.display();
    }
}

public class Main {
    public static void main(String[] args) {
        Library lib = new Library("Central Library");
        lib.showStaff("Alice");  
    }
}
```


✅ **Advantage:** Inner classes can access outer class **attributes and methods**, even if they are `private`.

* **Note**:A top-level class (not nested inside another class) cannot be static.
    ```java
    static class Outer {  
        // ❌ Compile-time error
    }
    ```
---