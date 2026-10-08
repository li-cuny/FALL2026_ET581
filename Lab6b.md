
# 6. Access Modifiers

Access modifiers control how class members are accessed.
| Modifier    | Access                    |
| ----------- | ------------------------- |
| `public`    | Everywhere                |
| `private`   | Same class only           |
| `protected` | comming soon|
| *(default)* | comming soon               |

Example using private:
```java
class Student {

    private String name;
    private int age;

    Student(String n, int a) {
        name = n;
        age = a;
    }

    void display() {
        System.out.println(name + " " + age);
    }
}
```

### Attempting to Access Private Variables
```java
public class Main {
    public static void main(String[] args) {

        Student s1 = new Student("Alice", 20);

        System.out.println(s1.name); // Error: cannot access private variable
        System.out.println(s1.age);  // Error: cannot access private variable
    }
}
```

* private member variables cannot be accessed from outside the class

* This helps protect object data



## 7. Getters and Setters (Encapsulation)

* **Getter**: A method that returns the value of a private field.

* **Setter**: A method that sets or updates the value of a private field.

They are used to encapsulate data, allowing controlled access to `private fields` from `other` classes.


```java
class Student {
    private String name;
    private int age;

    // Constructor
    Student(String n, int a) {
        name = n;
        age = a;
    }

    // Getter for name
    public String getName() {
        return name;
    }

    // Setter for name
    public void setName(String n) {
        name = n;
    }

    // Getter for age
    public int getAge() {
        return age;
    }

    // Setter for age
    public void setAge(int a) {
        age = a;
    }
}
```
* Using Getters and Setters
```java
public class Main {
    public static void main(String[] args) {
        Student s1 = new Student("Alice", 20);

        System.out.println(s1.getName());
        s1.setAge(21);
        System.out.println(s1.getAge());
    }
}
```
* Encapsulation is the principle of hiding data and providing controlled access.


## 8. Object in field or param
- A field of a class can itself be an object of another class.
```java
class Address {
    String city;
    String country;

    Address(String city, String country) {
        this.city = city;
        this.country = country;
    }

    void displayAddress() {
        System.out.println(city + ", " + country);
    }
}

class Student {
    String name;
    int age;
    Address address; // field is another class object

    Student(String name, int age, Address address) {
        this.name = name;
        this.age = age;
        this.address = address;
    }

    void display() {
        System.out.println("Name: " + name);
        System.out.println("Age: " + age);
        System.out.print("Address: ");
        address.displayAddress(); // calling method of field object
    }
}

public class Main {
    public static void main(String[] args) {
        Address a1 = new Address("New York", "USA");
        Student s1 = new Student("Alice", 20, a1);

        s1.display();
    }
}

- object in method parameter
```java
class Student {
    private String name;
    // Constructor
    public Student(String name) {
        this.name = name;
    }
    // Method that greets another Student
    public void greet(Student other) {
        System.out.println("Hello " + other.name + ", I am " + this.name + "!");
    }
}

public class Main {
    public static void main(String[] args) {
        Student s1 = new Student("Alice");
        Student s2 = new Student("Bob");

        s1.greet(s2); // Output: Hello Bob, I am Alice!
        s2.greet(s1); // Output: Hello Alice, I am Bob!
    }
}
```
### 9. Static Members

* The `static` keyword means the item belongs to the class, not to instances (objects).

* Static members (variables or methods) are shared among all objects of the class.

* You can access static members without creating an object.

```java
class Student {
    private String name;
    private int age;
    static int count = 0; // shared by all objects

    Student(String n, int a) {
        name = n;
        age = a;
        count++;
    }

    static void showCount() {
        System.out.println("Total Students: " + count);
    }
}
```

# 10. Memory
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
## 1. Method Area

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

## 2. Heap

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

## 3. Stack

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

## 4. Visual Summary
| Memory Area   | Stores                                     |
|---------------|-------------------------------------------|
| Method Area   | Class definitions & method code           |
| Heap          | Object instances & instance fields        |
| Stack         | Local variables & method call frames      |


