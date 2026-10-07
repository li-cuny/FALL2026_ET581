

## 1. Class & Object

### A **class is a blueprint**.

```java
class Student {

}
```
### An object is an instance of a class.

* Use the new keyword to create an object:
```java
Student student1 = new Student(); // instance 1 of Student class type
Student student2 = new Student(); // instance 2 of Student class type
```
| Class                                    | Object                         |
| ---------------------------------------- | ------------------------------ |
| Blueprint/template                       | Instance of a class            |
| `Student`                                | `student1`, `student2`         |


## 2. Class Members (member variables & member methods)

A class can contain:

* Fields (member variables) — store data
* Methods(member methods) — define behavior

```java
class Student {

    String name; // first member
    int age;     // second member

    void display() { // third member 
        System.out.println("Name: " + name);
        System.out.println("Age: " + age);
    }
}
```
### Using member veriables and methods
To access a member variable or member method through an object, use the dot (.) operator.
```java
object.memberVar;
object.memberMethod();
```
##### Example
```java
public class Main {
    public static void main(String[] args) {
        Student s1 = new Student();
        s1.name = "Alice"; 
        s1.age = 10;
        s1.display(); // display Name: Alice Age: 10

        Student s2 = new Student();
        s2.name = "Bob"; 
        s2.age = 20;
        s2.display(); // display Name: Bob Age: 20
    }
}
```
* Each object can store its own data.
* s1 and s2 are two different objects, so they can have different values for name and age.


## 3. Constructor

A constructor initializes object data when the object is created.
#### Student.java
```java
class Student {

    String name;
    int age;

    Student(String n, int a) {
        name = n;
        age = a;
    }

    void display() {
        System.out.println(name + " " + age);
    }
}
```
#### Main.java
```java
public class Main {
    public static void main(String[] args) {

        Student s1 = new Student("Alice", 20);

        s1.display();
    }
}
```
* Constructors run automatically when an object is created

### Default Constructor
*  A default constructor is a constructor that takes no parameters.

##### If you do not create any constructor in your class, Java automatically provides a default constructor.
```java
class Student {
    String name;
    int age;
    public static void main(String[] args){
        Student s = new Student(); // default constructor
    }
}
```
##### If you create any constructor yourself, Java does not automatically create the no-argument default constructor.
```java
class Student {
    String name;
    int age;

    Student(String name, int age) {
        this.name = name;
        this.age = age;
    }
    public static void main(String[] args){
        Student s = new Student();  // ❌ Error
    }
}
```

# 4. Array with Class Object
```java
Student s1 = new Student("John", 20); 
Student s2 = new Student("Mary", 21); 
Student s3 = new Student("David", 19); 
Student[] students = {s1, s2, s3}; 
for (int i = 0; i < students.length; i++) {
     students[i].display(); 
}
```

# 5. this Keyword

- The `this` keyword in Java is a reference variable that refers to the current object — the object whose method or constructor is being executed.


```java
class Student {
    String name;
    int age;

    Student(String name, int age) {
        this.name = name; // 'this' refers to current object
        this.age = age;
    }
    void display() {
        System.out.println(this.name + " " + this.age);
    }

}
```
```java
class Main {
    public static void main(String[] args){
        Student s1 = new Student("John", 20); // inside of Constructor this mean s1 object 
        Student s2 = new Student("Mary", 21); 
        Student s3 = new Student("David", 19);
        s1.display(); // inside of  method this mean s1 object
    }
}

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

