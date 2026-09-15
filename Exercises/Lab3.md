# **While Loop Practice Exercises**

## **Exercise 1 — Print Numbers 1 to 10**

Write a Java program that uses a `while` loop to print the numbers from **1 to 10**.

**Expected Output:**

```text
1
2
3
4
5
6
7
8
9
10
```

---

## **Exercise 2 — Print Numbers 10 to 1**

Write a Java program that uses a `while` loop to print the numbers from **10 down to 1**.

**Expected Output:**

```text
10
9
8
7
6
5
4
3
2
1
```

---

## **Exercise 3 — Print a String in Reverse Order**

Write a Java program that creates a `String` and uses a `while` loop to print the characters in **reverse order**.

**Example:**

```text
Input: Java
Output: avaJ
```

**Hint:**

- Use `length()` to find the length of the String.
- Use `charAt()` to access each character.
- Start from the last character and move toward the first character.

---

## **Exercise 4 — Print a String but Exclude a Character**

Write a Java program that reads a String from the user and prints the String **without a specified character**.

**Example:**

```text
Input: Java
Character to exclude: a

Output: Jv
```

---

## **Exercise 5 — Calculate the Sum from 1 to 100**

Write a Java program that uses a `while` loop to calculate and print the sum of the numbers from **1 to 100**.

**Expected Output:**

```text
Sum = 5050
```

---

## **Exercise 6 — Positive Number**

Write a Java program that asks the user to enter a number.

Keep asking the user to enter a number **while the number is less than or equal to 0**.

When the user enters a positive number, print:

```text
Valid number
```

**Example:**

```text
Enter a number: -5
Enter a number: 0
Enter a number: -10
Enter a number: 8
Valid number
```

---

## **Exercise 7 — Break and Continue with String**

Write a Java program that repeatedly asks the user to enter a word.

Use a `while` loop.

- If the user enters `"skip"`, use `continue` to **skip that word** and ask for another word.
- If the user enters `"quit"`, use `break` to **stop the loop**.
- Otherwise, print the word entered by the user.
- The comparison should be **case-insensitive**.

### **Example**

```text
Enter a word: Java
Java

Enter a word: skip

Enter a word: String
String

Enter a word: SKIP

Enter a word: Programming
Programming

Enter a word: QUIT
Program stopped.
```

### **Requirements**

- Use `while`
- Use `break`
- Use `continue`
- Use `equalsIgnoreCase()`
- Do not use a `for` loop

---

## **Exercise 8 — Caesar Cipher (Challenge)**

Write a Java program that encrypts a String by shifting each letter **3 positions forward** in the alphabet.

For example:

```text
A → D
B → E
C → F
```

Use a `while` loop to process each character.

### **Expected Output**

```text
Input: PROGRAMMING
Output: SURJUDPPLQJ
```

### **Hints**

- Use `charAt()` to access each character.
- Use `length()` to determine how many characters need to be processed.
- Use `% 26` to wrap around after `Z`.
- Use a `while` loop to process each character.
- Assume the input contains uppercase letters only.

### **Example of Wrapping**

```text
X → A
Y → B
Z → C
```