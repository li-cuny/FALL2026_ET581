
## String

* `String` is **not a primitive type**; it is a **class/object type** in Java.
* A `String` stores a **sequence of characters**.
* Strings are written inside **double quotes** (`" "`).

```java
String motto = "String is a sequence of chars.";
```

Here:

* `String` → data type (class)
* `motto` → variable
* `"String is a sequence of chars."` → String object/value


### Concatenation of Strings
* Using + operator (most common)
```java
String first = "Hello";
String second = "World";
String result = first + " " + second; // "Hello World"

first + 2026; //  "Hello2026" 
2026 + first; // "2026Hello"

```
* Using String.concat()
```java
String a = "Java";
String b = " Programming";
String result = a.concat(b);// "Java Programming"
```


### String methods

## 1.. `length()`
**Definition:**
```java
int length()
```
- Returns the number of characters in the string.

**Example:**
```java
String text = "Programming";
int len = text.length();  // len = 11
len = "Hi".length(); 
```
## 2. `equals()`
**Definition:**
```java
boolean equals(String other)
```
- Compares the content of the calling string with another string.

**Example:**
```java
String greeting = "Hello";
greeting.equals("Hello")//true 
```

## 3. `charAt()`
**Definition:**
```java
char charAt(int index);
```
- Returns the character at a specific index (starting at 0).

**Example:**
```java
String word = "Java";
char ch = word.charAt(2);  // ch = 'v'
```

## 4. `compareTo()` 
```java
int compareTo(String anotherString)
```
Compares two strings lexicographically (dictionary order) using Unicode values of characters.

* Return values
```
< 0 → calling string comes before anotherString

0 → strings are equal

> 0 → calling string comes after anotherString
```
```java
String a = "adventure";

a.compareTo("zoo");        // negative
a.compareTo("adventure"); // 0
a.compareTo("above");     // positive
```

| **Method**                      | **Use Case (What it’s used for)**                          | **Example Code**                       | **Result**   |
| ------------------------------- | ---------------------------------------------------------- | -------------------------------------- | ------------ |
| `length()`                      | Find number of characters in a string                      | `"Hello!".length()`                    | `6`          |
| `equals(String s)`              | Check if two strings are exactly the same (case-sensitive) | `"Hello".equals("Hello")`              | `true`       |
| `equalsIgnoreCase(String s)`    | Compare strings ignoring case                              | `"mary".equalsIgnoreCase("Mary")`      | `true`       |
| `toLowerCase()`                 | Convert all letters to lowercase                           | `"Hi Mary!".toLowerCase()`             | `"hi mary!"` |
| `toUpperCase()`                 | Convert all letters to uppercase                           | `"Hi Mary!".toUpperCase()`             | `"HI MARY!"` |
| `trim()`                        | Remove leading & trailing spaces                           | `"  Hmm  ".trim()`                     | `"Hmm"`      |
| `charAt(int i)`                 | Get character at a specific index                          | `"Hello".charAt(1)`                    | `'e'`        |
| `substring(int start)`          | Extract substring from index to end                        | `"AbcdefG".substring(2)`               | `"cdefG"`    |
| `substring(int start, int end)` | Extract substring between two indexes                      | `"AbcdefG".substring(2,5)`             | `"cde"`      |
| `indexOf(String s)`             | Find first occurrence of substring                         | `"Hi Mary!".indexOf("Mary")`           | `3`          |
| `indexOf(String s, int start)`  | Find substring starting from index                         | `"Mary, Mary".indexOf("Mary",1)`       | `6`          |
| `lastIndexOf(String s)`         | Find last occurrence of substring                          | `"Mary, Mary".lastIndexOf("Mary")`     | `6`          |
| `compareTo(String s)`           | Alphabetical comparison (case-sensitive)                   | `"apple".compareTo("banana")`          | Negative     |
| `compareToIgnoreCase(String s)` | Alphabetical comparison ignoring case                      | `"Apple".compareToIgnoreCase("apple")` | `0`          |

**Full method list:** [Java String API](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)

