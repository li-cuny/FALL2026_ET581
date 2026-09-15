# Loops in Java

## 1. While Loop
- A **while loop** repeats a block of code **as long as a condition is true**.

### Syntax:
```java
while (condition) {
    // code block to be executed
}
```

### Example1 : Repeat print
```java
System.out.println("Hello");
System.out.println("Hello");
System.out.println("Hello");
System.out.println("Hello");
System.out.println("Hello");
```
using while loop
```java
int count = 1;
while (count <= 5) {
    System.out.println("Hello");
    count++;
}
```


### Pseudocode for While Loop ( Machine Code )
```
LOOP_START:
    if (condition not true) jump to LOOP_END
    // code block to be executed
    jump to LOOP_START
LOOP_END:
```

---

## 2. Do...While Loop
- Executes the loop **body first**, then checks the condition.  
- This ensures the loop runs **at least once**.

### Syntax:
```java
do {
    // code block to be executed
} while (condition);
```

### Pseudocode:
```
LOOP_START:
    // code block to be executed
    if (condition true) jump to LOOP_START
LOOP_END:
```

---

### Example2 : print number
```java
int n = 0;
System.out.println(n); //0
n++;
System.out.println(n); //1
n++;
System.out.println(n); //2
n++;
System.out.println(n); //3
n++;
System.out.println(n); //4
```
using while loop
```java
int n = 0;
while (n < 5) {
    System.out.println(n);
    n++;
}
```

## 3. Break
- **Purpose:** Exit the loop immediately, regardless of the condition.  
- Think of it as **“break out of the loop.”**

```java
int i = 1;

while (i <= 5) {

    if (i == 3) {
        break;   // exit the loop immediately
    }
    System.out.println(i);
    i++;
}
```

### Output

```text
1
2
```
## 4. Continue
- **Purpose:** Skip the **current iteration** and move to the next one.  
- Think of it as **“continue to the next round.”**

```java
int i = 1;

while (i <= 5) {

    if (i == 3) {
        break;   // exit the loop immediately
    }
    System.out.println(i);
    i++;
}
```
### Output

```text
1
2
4
5
```

### Key Difference
- `break` → jumps **out of the loop**  
- `continue` → jumps to **loop update** (`i++`) and then back to the start
