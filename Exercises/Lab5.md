# Java Arrays – Practice Exercises

### 1. Print Elements
Create an array and print all elements using:
- a basic `for` loop  
- an enhanced `for-each` loop  

Create an array:

```java
int[] numbers = {1, 2, 3, 4, 5};
```
Expected output: 
```
output: 1 2 3 4 5
```

---
### 2. Print Elements in reverse order
Create an array of 5 integers and print all elements in reverse order using:
- a basic `for` loop  

Create an array:

```java
int[] numbers = {1, 2, 3, 4, 5};
```

Expected output: 
```
output: 5 4 3 2 1
```
---

### 3. Sum of Elements
Create an method that takes an int[] and returns all elements sum :

```java
int sum(int[] array);
```

### 4. Find the Largest Number

Create an method that takes an int[] and returns largest number.

```
int largestNumber(int[] array);
```
example:
```
int[] numbers = {3, 8, 2, 10, 5};
int max = largestNumber(numbers); // max = 10;
```
### 5. Count Even Numbers
create method that returns count of even numbers in the array.
```
int countEven(int[] array);
```
```java
int[] numbers = {4, 7, 9, 12, 6, 3};
int count = countEven(numbers); // count = 3
```

### 6. Reverse an Array (Without Creating New Array)
```java
int[] numbers = {1, 2, 3, 4, 5};
```
Modify the array so it becomes:
```
{5, 4, 3, 2, 1}
```

### 7. Linear Search
```java
int[] numbers = {2, 4, 6, 8, 10};
```

Ask the user for a number and check if it exists in the array.

If found:
```
Number found at index X
```
If not found:
```
Number not found
```
### 8. Remove Duplicates in sorted array
```java
int[] numbers = {1, 2, 2, 3, 4, 4, 5};
```
Print only unique values.

Expected Output:
```
1 2 3 4 5
```

### 9. Check if Array is Sorted

Determine whether the array is sorted in ascending order.

Examples:
```
{1, 2, 3, 4} → Sorted
{1, 3, 2, 4} → Not sorted
```