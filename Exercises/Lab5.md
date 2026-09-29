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


### 6. Linear Search
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
### 7. Remove Duplicates in sorted array
```java
int[] numbers = {1, 2, 2, 3, 4, 4, 5};
```
Print only unique values.

Expected Output:
```
1 2 3 4 5
```

### 8. Check if Array is Sorted

Write a method that returns boolean value of whether the array is sorted in ascending order.
```java
boolean isSorted(int[] array);
```
Examples:

```java 
int[] numbers = {1, 2, 3, 4};
System.out.println(isSorted(numbers));// true;
numbers = {1, 3, 2, 4};
System.out.println(isSorted(numbers));// false;
```