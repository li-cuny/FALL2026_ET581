# 📝 Practice Exercises – Lab 2
## Java `String` Methods

### Instructions

1. Write a complete Java program.
2. Create the necessary `String` variables.
3. Use the **String method specified in the question**.
4. Print the result using `System.out.println()`.
5. Test your program with the given example.
6. Make sure your program compiles and runs without errors.

> **Reminder:** String indexes start at `0`, not `1`.

For example:

```text
"Hello"
 01234
```

- `H` → index `0`
- `e` → index `1`
- `l` → index `2`
- `l` → index `3`
- `o` → index `4`

---

## Exercise 1 – String Length

Write a program that asks the user to enter a string.

### Requirements

1. Ask the user to enter a string.
2. Store the user's input in a `String` variable.
3. Use the `length()` method to find the number of characters.
4. Print the length.

### Example

```text
Enter a string: Programming
Length: 11
```

**Method to use:** `length()`

---

## Exercise 2 – Compare Two Strings

Write a program that asks the user to enter two strings and determines whether they are equal.

### Requirements

1. Ask the user for the first string.
2. Ask the user for the second string.
3. Store both inputs in `String` variables.
4. Use the `equals()` method to compare the two strings.
5. Print whether the strings are equal.

### Example

```text
Enter first string: Java
Enter second string: Java
The strings are equal.
```

Try your program again with:

```text
Java
java
```

Notice that `equals()` is **case-sensitive**.

**Method to use:** `equals()`

---

## Exercise 3 – Check a Username

Write a program that asks the user to enter a username.

Assume the correct username is:

```text
student
```

### Requirements

1. Ask the user to enter a username.
2. Compare the user's input with `"student"`.
3. Use `equalsIgnoreCase()` so that uppercase and lowercase letters do not matter.
4. Print whether the username is correct.

### Example

```text
Enter username: STUDENT
Username accepted.
```

The following should all be accepted:

```text
student
Student
STUDENT
sTuDeNt
```

**Method to use:** `equalsIgnoreCase()`

---

## Exercise 4 – Change Letter Case

Write a program that asks the user to enter a string.

### Requirements

1. Ask the user to enter a string.
2. Print the original string.
3. Convert the string to lowercase using `toLowerCase()`.
4. Print the lowercase version.
5. Convert the string to uppercase using `toUpperCase()`.
6. Print the uppercase version.

### Example

```text
Enter a string: Java Programming

Original: Java Programming
Lowercase: java programming
Uppercase: JAVA PROGRAMMING
```

**Methods to use:**

- `toLowerCase()`
- `toUpperCase()`

---

## Exercise 5 – Remove Extra Spaces

Write a program that asks the user to enter a string with spaces before and/or after the text.

### Requirements

1. Ask the user to enter a string.
2. Store the input in a `String` variable.
3. Print the original length.
4. Use `trim()` to remove spaces from the beginning and end of the string.
5. Print the new string.
6. Print the new length.

### Example

```text
Enter a string:    Hello Java    

Original length: 15
New string: Hello Java
New length: 10
```

### Important

`trim()` removes spaces at the **beginning and end**.

It does not remove spaces between words.

For example:

```text
"   Hello   Java   "
```

becomes:

```text
"Hello   Java"
```

**Methods to use:**

- `trim()`
- `length()`

---

## Exercise 6 – First and Last Characters

Write a program that prints the first and last characters of:

```text
Programming
```

### Requirements

1. Store `"Programming"` in a `String` variable.
2. Find the first character using `charAt()`.
3. Find the last character using `charAt()`.
4. Print both characters.

### Expected Output

```text
First character: P
Last character: g
```

### Hint

The first character is always at index:

```text
0
```

The last character is at:

```text
length - 1
```

**Methods to use:**

- `charAt()`
- `length()`

---

## Exercise 7 – Extract Part of a String

Extract the word:

```text
happy
```

from:

```text
unhappy
```

### Requirements

1. Store `"unhappy"` in a `String` variable.
2. Determine where `"happy"` begins.
3. Use `substring()` to extract `"happy"`.
4. Print the result.

### Expected Output

```text
happy
```

### Hint

Look carefully at the indexes:

```text
unhappy
0123456
```

The `h` begins at index `2`.

**Method to use:** `substring()`

---

## Exercise 8 – Extract a Word

Extract:

```text
computer
```

from:

```text
computer science
```

### Requirements

1. Store `"computer science"` in a `String` variable.
2. Use `substring()` to extract only `"computer"`.
3. Print the extracted word.

### Expected Output

```text
computer
```

### Hint

Remember that `substring(start, end)` includes the character at `start` but does **not** include the character at `end`.

**Method to use:** `substring()`

---

## Exercise 9 – Find a Word

Find the position of `"programming"` in:

```text
Java programming is fun
```

### Requirements

1. Store the sentence in a `String` variable.
2. Use `indexOf()` to search for `"programming"`.
3. Print the index where `"programming"` begins.

### Expected Output

```text
Index: 5
```

### Hint

Spaces are characters too, so they count when determining the index.

**Method to use:** `indexOf()`

---

## Exercise 10 – Find the Second Occurrence

Given the string:

```text
one two one two one
```

find the index of the **second** occurrence of `"one"`.

### Requirements

1. Store the string in a `String` variable.
2. Find the first occurrence of `"one"`.
3. Use `indexOf()` again to find the next occurrence.
4. Print the index of the second `"one"`.

### Hint

`indexOf()` can start searching from a specific index.

You can use:

```java
indexOf("one", startingIndex)
```

The second search should begin **after the first `"one"`**.

### Expected Output

```text
Second "one" starts at index: 8
```

**Method to use:** `indexOf()`

---

## Exercise 11 – Find the Last Occurrence

Given:

```text
red blue red green red
```

find the position of the **last** `"red"`.

### Requirements

1. Store the sentence in a `String` variable.
2. Use `lastIndexOf()` to find the last occurrence of `"red"`.
3. Print the index.

### Expected Output

```text
Last "red" starts at index: 15
```

**Method to use:** `lastIndexOf()`

---

## Exercise 12 – Alphabetical Comparison

Write a program that asks the user to enter two words.

Use `compareTo()` to determine which word comes first alphabetically.

### Requirements

1. Ask the user for two words.
2. Store them in two `String` variables.
3. Use `compareTo()` to compare the two strings.
4. If the result is:
   - negative → the first string comes first.
   - `0` → the strings are equal.
   - positive → the second string comes first.
5. Print an appropriate message.

### Example

```text
Enter first word: apple
Enter second word: banana

apple comes first alphabetically.
```

**Method to use:** `compareTo()`

---

## Exercise 13 – Case-Insensitive Comparison

Compare:

```text
Hello
```

and:

```text
hello
```

using `compareToIgnoreCase()`.

### Requirements

1. Store `"Hello"` in one `String` variable.
2. Store `"hello"` in another `String` variable.
3. Use `compareToIgnoreCase()`.
4. Determine the result.
5. Print whether the strings are equal when case is ignored.

### Expected Output

```text
The strings are equal.
```

### Question to think about

What is the difference between:

```java
compareTo()
```

and:

```java
compareToIgnoreCase()
```

**Method to use:** `compareToIgnoreCase()`

---

# Exercise 14 ⭐ Mini Challenge

Complete the following string-processing task.

Start with:

```text
"   I hate text processing!   "
```

### Step 1 – Store the String

Create a `String` variable containing:

```text
"   I hate text processing!   "
```

---

### Step 2 – Remove the Extra Spaces

Use `trim()` to remove the spaces at the beginning and end.

After this step, the string should be:

```text
I hate text processing!
```

---

### Step 3 – Replace a Word

Use `replace()` to change:

```text
hate
```

to:

```text
love
```

After this step, the string should be:

```text
I love text processing!
```

---

### Step 4 – Print the Final Result

Print the final string.

### Expected Output

```text
I love text processing!
```

### Methods to use

You should use:

```text
trim()
replace()
```

### Challenge

Try to complete the entire task using **one String variable** and updating its value after each step.

---

# 📌 String Methods Used in This Lab

| Method | Purpose |
|---|---|
| `length()` | Find the number of characters |
| `equals()` | Compare two strings |
| `equalsIgnoreCase()` | Compare strings without considering case |
| `toLowerCase()` | Convert to lowercase |
| `toUpperCase()` | Convert to uppercase |
| `trim()` | Remove leading and trailing spaces |
| `charAt()` | Get a character at a specific index |
| `substring()` | Extract part of a string |
| `indexOf()` | Find the first occurrence |
| `lastIndexOf()` | Find the last occurrence |
| `compareTo()` | Compare strings alphabetically |
| `compareToIgnoreCase()` | Compare strings alphabetically, ignoring case |
| `replace()` | Replace characters or text |

## ⚠️ Important Reminder

A `String` is an **object**, not a primitive type.

Also remember:

```java
String s = "Hello";
```

The String's characters have indexes:

```text
 H   e   l   l   o
 0   1   2   3   4
```

So:

```java
s.charAt(0)
```

gives:

```text
H
```

and:

```java
s.charAt(4)
```

gives:

```text
o
```