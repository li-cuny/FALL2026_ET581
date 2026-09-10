# 📝 Java Practice Exercises

## Exercise 1 — Compare Two Numbers

Write a program that asks the user to enter **two integers**.

Display whether:

1. The first number is greater than the second.
2. The first number is less than the second.
3. The two numbers are equal.

**Example:**

```text
Enter first number: 20
Enter second number: 10

First number is greater: true
First number is less: false
Numbers are equal: false
```

---

## Exercise 2 — Compare Strings with `equals()`

Write a program that asks the user to enter two strings.

Use `.equals()` to determine whether the strings are equal.

**Example:**

```text
Enter first string: Hello
Enter second string: Hello

Strings are equal: true
```

> Do not use `==` to compare the contents of two `String` objects.

---

## Exercise 3 — AND `&&`

Write a program that asks the user to enter their age.

Check whether the age is between **18 and 65**, inclusive.

Use the logical AND operator `&&`.

**Example:**

```text
Enter age: 25
Eligible: true
```

---

## Exercise 4 — OR `||`

Write a program that asks the user to enter a day number.

A student has class if the day is:

- `1` = Monday
- `3` = Wednesday
- `5` = Friday

Use the logical OR operator `||`.

**Example:**

```text
Enter day number: 3
Has class: true
```

---



## Exercise 5 — `if/else`

Write a program that asks the user to enter an integer.

Use `if/else` to determine whether the number is **even or odd**.

**Example:**

```text
Enter a number: 7
Odd number
```

---

## Exercise 6 — Positive, Negative, or Zero

Write a program that asks the user to enter an integer.

Use `if`, `else if`, and `else` to determine whether the number is:

- Positive
- Negative
- Zero

**Example:**

```text
Enter a number: -5
Negative
```

---


## Exercise 7 — Even or Odd Using Ternary

Rewrite the even/odd exercise using the **ternary operator** instead of `if/else`.

**Example:**

```text
Enter a number: 8
Even
```

---

## Exercise 8 — Pass or Fail

Ask the user to enter a grade.

Use the ternary operator to display:

- `"Pass"` if the grade is `60` or higher
- `"Fail"` otherwise

**Example:**

```text
Enter grade: 75
Pass
```

---

## Exercise 9 — Day of the Week

Ask the user to enter a number from `1` to `7`.

Use `switch` to display the corresponding day.

| Number | Day |
|---|---|
| 1 | Monday |
| 2 | Tuesday |
| 3 | Wednesday |
| 4 | Thursday |
| 5 | Friday |
| 6 | Saturday |
| 7 | Sunday |

For any other number, display:

```text
Invalid day
```

**Example:**

```text
Enter day number: 4
Thursday
```

---

## Exercise 10 — Simple Calculator

Ask the user to enter:

1. First number
2. Second number
3. An operator: `+`, `-`, `*`, or `/`

Use `switch` to perform the selected operation.

**Example:**

```text
Enter first number: 10
Enter second number: 5
Enter operator: *

Result: 50
```

---

## Exercise 11 — Separate Words

Given:

```java
String sentence = "Java is easy to learn";
```

Use `StringTokenizer` to print first three word on a separate line.

**Expected output:**

```text
Java
is
easy
```



## Exercise 12 — Comma-Separated Data

Given:

```java
String data = "apple,banana,orange,grape";
```

Create a `StringTokenizer` using `,` as the delimiter.

Print first two fruit on a separate line.

**Expected output:**

```text
apple
banana
```

---
