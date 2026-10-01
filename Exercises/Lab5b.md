# 2D array

## **Exercise 1 — Print All Elements**

Create the following 2D array:

```java
int[][] arr = {
    {1, 2, 3},
    {4, 5, 6},
    {7, 8, 9}
};
```

Use **nested `for` loops** to print all elements.

### **Expected Output**

```text
1 2 3
4 5 6
7 8 9
```

---

## **Exercise 2 — Find the Largest Number**

Given:

```java
int[][] arr = {
    {12, 5, 8},
    {20, 3, 15},
    {7, 25, 10}
};
```

Use nested `for` loops to find the largest number.

### **Expected Output**

```text
Largest: 25
```



---

## **Exercise 3 — Print One Row**

Given:

```java
int[][] arr = {
    {1, 2, 3},
    {4, 5, 6},
    {7, 8, 9}
};
```

Ask the user to enter a row number.

Print all elements in that row.

### **Example Input**

```text
Enter row: 1
```

### **Expected Output**

```text
4 5 6
```

---

## **Exercise 4 — Print One Column**

Given:

```java
int[][] arr = {
    {1, 2, 3},
    {4, 5, 6},
    {7, 8, 9}
};
```

Ask the user to enter a column number.

Print all elements in that column.

### **Example Input**

```text
Enter column: 2
```

### **Expected Output**

```text
3
6
9
```

---

## **Exercise 5 — Jagged Array**

Create this jagged array:

```java
int[][] arr = {
    {1, 2},
    {3, 4, 5},
    {6},
    {7, 8, 9, 10}
};
```

Use nested `for` loops to print all elements.

### **Expected Output**

```text
1 2
3 4 5
6
7 8 9 10
```

**Hint:** Use `arr.length` for the number of rows and `arr[r].length` for the number of elements in each row.

---

## **Exercise 6 — Replace Negative Numbers**

Given:

```java
int[][] arr = {
    {1, -2, 3},
    {-4, 5, -6},
    {7, -8, 9}
};
```

Use nested `for` loops to replace every negative number with `0`.

### **Expected Output**

```text
1 0 3
0 5 0
7 0 9
```

---

## **Exercise 7 — 2D Array sum**

Create a method:

```java
static int sum(int[][] arr)
```

The method should return the sum of all elements in the 2D array.

Given:

```java
int[][] numbers = {
    {1, 2, 3},
    {4, 5, 6},
    {7, 8, 9}
};
```

### **Expected Output**

```text
Sum: 45
```
## **Exercise 8 — 2D String Array to Lengths — Method Exercise

Write a method named `getLengths()` that receives a 2D `String` array and returns a 2D `int` array containing the length of each String.

## Given Array

```java
String[][] words = {
    {"cat", "apple", "dog"},
    {"banana", "java", "computer"},
    {"hi", "school", "book"}
};
```

## Method

Write the following method:

```java
static int[][] getLengths(String[][] words)
```

The method should return:

```text
3 5 3
6 4 8
2 6 4
```

## Requirements

* Use **nested `for` loops** inside the method.
* Create and return a new `int[][]` array.
* Use `.length()` to get the length of each String.
* Do not change the original `String[][]` array.
* Print the returned `int[][]` in `main()`.

## Expected Output

```text
3 5 3
6 4 8
2 6 4
```

---
