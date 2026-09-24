

## Math Class in Java
| Method   | Description             |
| -------- | ----------------------- |
| max(a,b) | Returns larger value    |
| min(a,b) | Returns smaller value   |
| abs(x)   | Absolute value          |
| sqrt(x)  | Square root             |
| pow(a,b) | Power                   |
| random() | Random number [0.0–1.0) |
| round(x) | Rounds number           |
| ceil(x)  | Rounds up               |
| floor(x) | Rounds down             |

Math class java doc: https://docs.oracle.com/javase/8/docs/api/?java/lang/Math.html
 
- `(int)(Math.random() * 101)` → random number [0,100]  

---
## Generating Random Numbers

### Using `Math.random()`
```java
double r = Math.random();
int n = (int)(Math.random() * 10); // 0 to 9
```

### Using `Random` Class
```java
import java.util.Random;

Random rand = new Random();

// Random double 0.0 <= x < 1.0
double rDouble = rand.nextDouble();

// Random int between 0 and 9
int rInt = rand.nextInt(10);

// Random boolean
boolean rBool = rand.nextBoolean();
```
- More versatile than `Math.random()`.
- Can set a **seed** for reproducible results.
    - If the formula starts with the same seed, it will produce the same sequence of numbers.
```java
import java.util.Random;

Random r = new Random(10);   // 10 is the seed
System.out.println(r.nextInt(100));
System.out.println(r.nextInt(100));
```

---
# Nested for loop

# Nested Loop in Java

A nested `for` loop is useful when you have **two levels of repetition**.

```java
public static void printRowOfHello() {
    for (int j = 1; j <= 4; j++) { // repeat Hello 4 times
        System.out.print("Hello ");
    }
    System.out.println();
}

public static void main(String[] args) {
    for (int i = 1; i <= 3; i++) { //repeat rowOfHello 3 times 
        printRowOfHello();
    }
}
```
the above code is the same as the below code.

```java
for (int i = 1; i <= 3; i++) {
    for (int j = 1; j <= 4; j++) {
        System.out.print("Hello ");
    }
    System.out.println();
}
```

### Output

```text
Hello Hello Hello Hello
Hello Hello Hello Hello
Hello Hello Hello Hello
```

## Example 2 
```java
for (int i = 1; i <= 3; i++) {

    for (char ch = 'A'; ch <= 'D'; ch++) {
        System.out.print(ch + " ");
    }

    System.out.println();
}
```
```
A B C D
A B C D
A B C D
```