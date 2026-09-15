# Loops in Java

## 1. For Loop
- A **for loop** is a simpler way to handle loops with:  
  - **Initialization**  
  - **Condition**  
  - **Update**

### While Loop Equivalent
```java
int i = 0;                  // initialization
while (i < 5) {             // condition
    System.out.println("i = " + i);
    i++;                    // update
}
```

### Simplified For Loop
```java
for (int i = 0; i < 5; i++) {
    System.out.println("i = " + i);
}
```

### Why Use a For Loop?
1. **Easy to read and shorter** → all in one line  
2. **Prevent mistakes** → less chance of forgetting the update (`i++`)  
3. **Intent is clear**  
   - `for` → repeat a fixed number of times  
   - `while` → repeat until a condition becomes false (not necessarily a fixed count)


### multiple statement 
In a for loop, when you have more than one statement in the initialization or update sections, you separate them with commas.

#### Important points:
The **condition cannot have commas**, it must be a single boolean expression.
```java
for (int x = 1, y = 5; x <= 3 && y >= 3; x++, y--) {
    System.out.println("x = " + x + ", y = " + y);
}
```
output:
```
x = 1, y = 5
x = 2, y = 4
x = 3, y = 3
```
---
