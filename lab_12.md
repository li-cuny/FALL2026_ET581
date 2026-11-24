# Java Exceptions

## 1. What Is an Exception?
An **exception** is an event that disrupts the normal flow of a program. It occurs when something unexpected happens during execution.

Common examples:
- Divide by zero
- Accessing invalid array index
- File not found
- Null pointer access

Java uses exceptions to handle these errors safely.

---

## 2. Why Exceptions Are Needed
- Prevent program crashes
- Show meaningful error messages
- Allow alternative actions
- Keep the program running safely

Example of a crash without exception handling:
```java
int x = 10 / 0; // ArithmeticException
System.out.println("Done"); // never prints
```

---

## 3. Types of Exceptions

### **A. Checked Exceptions**
Handled at compile time. These represent external problems.

Examples:
- `IOException`
- `FileNotFoundException`
- `InterruptedException`

### **B. Unchecked Exceptions (Runtime Exceptions)**
Caused by programming mistakes.

Examples:
- `ArithmeticException`
- `NullPointerException`
- `ArrayIndexOutOfBoundsException`
- `NumberFormatException`

---

## 4. The try-catch Block
Used to handle exceptions.

### Syntax:
```java
try {
    // Code that may throw an exception
} catch (ExceptionType e) {
    // Handling code
}
```

### Example:
```java
try {
    int x = 10 / 0;
} catch (ArithmeticException e) {
    System.out.println("Cannot divide by zero!");
}
```

---

## 5. Multiple Catch Blocks
You can catch different exceptions separately.

```java
try {
    int num = Integer.parseInt("abc");
    int x = 10 / 0;
} catch (NumberFormatException e) {
    System.out.println("Invalid number format");
} catch (ArithmeticException e) {
    System.out.println("Division problem");
}
```

> Always catch more specific exceptions first.

---

## 6. The finally Block
The `finally` block **always executes**, whether an exception occurs or not.

Common use: closing files, database connections.

```java
try {
    FileReader fr = new FileReader("data.txt");
} catch (Exception e) {
    System.out.println("Error opening file");
} finally {
    System.out.println("Cleaning up resources...");
}
```

---

## 7. The throws Keyword
If a method does not want to handle an exception, it can declare it using `throws`.

```java
public void readFile() throws IOException {
    FileReader fr = new FileReader("data.txt");
}
```

This tells the caller to handle the exception.

---

## 8. Throwing Exceptions Manually
You can throw exceptions using `throw`.

```java
if (age < 18) {
    throw new IllegalArgumentException("Age must be 18+");
}
```

---

## 9. Custom Exceptions
Create your own exception class.

```java
class AgeException extends Exception {
    public AgeException(String message) {
        super(message);
    }
}
```

Usage:
```java
if (age < 18) {
    throw new AgeException("Not old enough");
}
```


## Summary
- Exceptions represent unexpected events
- try/catch handles errors safely
- finally always runs
- throws delegates(passing) handling
- Custom exceptions allow domain-specific errors

Java exception handling ensures programs run reliably and safely.
