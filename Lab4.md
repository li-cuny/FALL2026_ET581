# Function & Scope

## **Methods** ( Functions )

- A **function** is a block of code that is executed when it is called.
- A **method** is a function that is defined inside a **class**.
- **Benefit:** Methods allow us to **reuse code** instead of writing the same code multiple times.
- In Java, a function is a **method**.

### Syntax
```java
public class Main {
    static void myMethod() {
        // code
    }
}
```

### Parameters & Arguments
- Parameter = placeholder
- Argument = actual value

Example:
```java
static void add(int a, int b) {
    System.out.println(a+b);
}

add(10, 20);
// int a and int b → parameters
// 10 and 20 → arguments
```
* If a parameter has a `non-primitive type` (such as String, an array, or a class object), the argument passed to it is a reference value. Java passes a copy of that reference.

### Return Values
- Use a return type instead of `void`.  
```java
static int add(int a, int b) {
    return a + b;
}
```

### Method Overloading
having multiple methods with the `same name` but `different parameters` in the same class.

```java
int square(int x);
double square(double x);
```

⚠️ Key Notes

* Overloading methoed is determined at compile time.

* Return type alone cannot distinguish overloaded methods.
```java
static int add(int a, int b) {
    return a + b;
}
static double add(int a, int b) {
    return (double) a + b;
}
//error: method add(int,int) is already defined
```

---

## Scope
the part of a program where a variable is visible (can be accessed/used)
### 1. Class Scope (Global to the class)

Variables declared inside a class but outside methods/blocks.

Known as `fields` or `instance variables`.

Accessible by all methods in that class.
```java
class Example {
    static final int PI = 3.14; // class scope 
    static final int TOTAL_MONTHS_IN_A_YEAR = 12; // class scope

    static void print() {
        System.out.println(PI); // accessible here
    }
}
```

### 2. Method Scope (Local variables)

Variables declared inside a method.

- Exist only while the method runs.

- Not accessible from outside the method.
```java
class Example {
    void show() {
        int y = 20; // method scope
        System.out.println(y);
    }
    // System.out.println(y); ❌ ERROR (y not visible here)
}
```

### 3. Block Scope

Variables declared inside `{ }` (if, loop, etc.) are visible only in that block.
```java
class Example {
    void test() {
        if (true) {
            int z = 30; // block scope
            System.out.println(z);
        }
        // System.out.println(z); ❌ ERROR (z not visible outside the block)
    }
}
```
### 4. Loop Scope

A loop variable is accessible only within the loop.
```java
for (int i = 0; i < 5; i++) {
    System.out.println(i); // i is valid here
}
// System.out.println(i); ❌ ERROR
```
### 5. Parameter Scope

Method parameters are treated as local variables.
```java
void greet(String name) {
    System.out.println("Hello " + name); // name is valid only here
}
```

⚠️ Key Notes

* Java does not allow using a variable before declaration.
* Java prevents duplicate local variable names in the same method to avoid confusion about which variable should be used.

### 6. Local Variable Redeclaration

A local variable cannot be redeclared in a nested block if the same variable name already exists in the enclosing method.
```java
void test() {
    int x = 10;
    {
        int x = 20; // ❌ ERROR: cannot redeclare x in same scope
    }
}
```
