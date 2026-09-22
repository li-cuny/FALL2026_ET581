
## 1. Class Scope/Param Scope/Method Scope — Time Conversion

Create the following class-scope constants:

```java
static final int MINUTES_IN_AN_HOUR = 60;
static final int HOURS_IN_A_DAY = 24;
static final int SECONDS_IN_A_MINUTE = 60;
```

Write a method called `convertTime()` that takes the total number of seconds as a parameter.

The method should calculate and print how many:

- Days
- Hours
- Minutes
- Seconds

are represented by the total number of seconds.

### Example

```java
convertTime(90061);
```

### Expected Output

```text
Days: 1
Hours: 1
Minutes: 1
Seconds: 1
```

**Requirement:** Use the class-scope constants in your `convertTime()` method instead of directly using `60` or `24`.


---

## 2. Block Scope — Find the Error and fix

A game gives a player a bonus message when their score is 100 or higher.

Look at the following code:

```java
import java.util.Scanner;

public class Main {

    public static void main(String[] args) {

        Scanner input = new Scanner(System.in);

        System.out.print("Enter your score: ");

        int score = input.nextInt();

        if (score >= 100) {

            String message = "You unlocked a bonus!";

            System.out.println(message);

        }

        System.out.println(message);

    }

}
```

### Questions

1. Does this program compile?
2. If there is an error, which line causes the error?
3. Why does the error occur?
4. What is the scope of the variable `message`?
5. How can you fix the program?

---

## 3. Loop Scope — Find the Error and fix

Look at the following code:

```java
public class Main {

    public static void main(String[] args) {

        int i = 1;

        while (i <= 5) {

            int number = i * 10;

            System.out.println(number);

            i++;

        }

        System.out.println("Last number: " + number);

    }

}
```

### Questions

1. Does this program compile?
2. If there is an error, which line causes the error?
3. Why does the error occur?
4. What is the scope of the variable `number`?
5. How can you fix the program?




## Exercise 4 — Simple Calculator Methods

Write a Java program with four methods:

```java
add()
subtract()
multiply()
divide()
```

Each method should:

- Take two `double` parameters.
- Return the result.
- Be called from `main()`.

### Example

```java
System.out.println(add(10, 5));
System.out.println(subtract(10, 5));
System.out.println(multiply(10, 5));
System.out.println(divide(10, 5));
```

### Expected Output

```text
15.0
5.0
50.0
2.0
```

---
## **Exercise 5 — Replace One Character with `*`**

Write a Java program that asks the user to enter a **String of any length**.

Write a method that replaces one character with `*` at a given position.

Use a `for` loop in `main()` to call the method for each character in the String, starting from the first character and moving to the last character.

### **Example Input**

```text
abcdef
```

### **Expected Output**

```text
*bcdef
a*cdef
ab*def
abc*ef
abcd*f
abcde*
```

### **Requirements**

- Create a method to replace a character with `*`.
- The method should take the String and the character position as parameters.
- The method should return the modified String.
- Use a `for` loop to call the method for each position.
- The String can be **any length**.
