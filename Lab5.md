# Arrays


## 1. Definition
A data structure that stores a fixed number of elements of the same type, accessible by an index.

**Key Points**
- **Same type**: All elements must be of the same data type (e.g., all `int`, all `String`).
- **Fixed size**: Once created, the length of the array cannot change.
- **Indexed**: Each element is identified by a position number (index), starting at 0.
- **Contiguous memory**: Elements are stored next to each other in memory.

```java
int[] numbers = {10, 20, 30, 40};
System.out.println(numbers[0]); // prints 10
System.out.println(numbers[3]); // prints 40
```

---

## 2. Declaration & Creation

**Declare an array variable only (no size, no values yet):**
```java
int[] numbers;   // Preferred style
int numbers[];   // Also valid (C-style)
```

**Declare an array + create array object(size known, default values assigned):**
```java
int[] numbers = new int[5];
// Creates array of 5 integers, default values = 0
```

**Default values in arrays**

| Data Type    | Default Value |
|--------------|---------------|
| byte         | 0             |
| int          | 0             |
| long         | 0L            |
| float        | 0.0f          |
| double       | 0.0d          |
| char         | '\u0000' (null character) |
| boolean      | false         |
| Reference types (e.g., String, objects) | null |

**Declare an array + create array object +  init values:**
```java
int[] numbers = {10, 20, 30, 40, 50};
String[] cars = {"Volvo", "BMW", "Ford"};
```

**Two-step (declare first, assign later):**
```java
int[] numbers;
numbers = new int[]{10, 20, 30, 40, 50};
```
### Ways to Create Arrays

| Way | Syntax | Notes |
|-----|-------|------|
| With values | `int[] a = {1, 2, 3};` <br> or `int[] a = new int[]{1, 2, 3};` ✅ | Use when you know values |
| With size only | `int[] a = new int[3];` ✅ | Creates array with default values (`0` for int) |
| Size + values | `int[] a = new int[3]{1,2,3};` ❌ | Not allowed in Java |
---

## 3. Access & Assign
```java
int[] nums = new int[3];
nums[0] = 10;
System.out.println(nums[0]); // prints 10
```

---

## 4. `.length` Property
- `.length` gives the size of the array.
- **Note**: `.length` is a **property**, not a method.  
  ~~`.length()`~~ ❌

```java
int [] myNum = {10, 20, 30, 40};
System.out.println(myNum.length); // prints 4
```

---

## 5. Looping Through Arrays

### Basic `for` loop  
Uses index to access elements.
```java
int[] numbers = {10, 20, 30, 40};

for (int i = 0; i < numbers.length; i++) {
    System.out.println("Index " + i + ": " + numbers[i]);
}
```

### Enhanced `for-each` loop  
Shorter, no index, but cannot change array elements directly.
```java
for (int num : numbers) {
    System.out.println(num);
}
```

✅ Use **basic for loop** if you need index or want to update elements.  
✅ Use **enhanced for-each** for simple read-only traversal.  

---






## 6. Shallow Copy vs Deep Copy

### Shallow Copy
- Copies **reference only**.
- Both variables point to the **same array**.
```java
int[] a = {1, 2, 3};
int[] b = a;  // shallow copy
b[0] = 99;

System.out.println(a[0]); // 99
```

### Deep Copy
- Creates a **new array** and copies all values.
- Arrays are **independent**.
```java
int[] a = {1, 2, 3};
int[] b = new int[a.length];

for (int i = 0; i < a.length; i++) {
    b[i] = a[i];
}

b[0] = 99;

System.out.println(a[0]); // 1
System.out.println(b[0]); // 99
```
## 7. array with method 
* array as param
```
static void method(int[] array){
    // print array
}
static void main(String[] args){
    int[] a = {1, 2, 3};
    method(a);
}
```
* method return array
```
static int[] method(){
    int[] b = {1, 2, 3};
    return b;
}
static void main(String[] args){
    int a[] = method(); 
}
```

---

## 7. Arrays Utility Class (`java.util.Arrays`)

| Method | Description | Example |
|--------|-------------|---------|
| `Arrays.fill(array, value)` | Fill array with value | `Arrays.fill(arr, 1);` |
| `Arrays.sort(array)` | Sort array ascending | `Arrays.sort(arr);` |
| `Arrays.copyOf(array, newLength)` | Copy array with new size | `int[] newArr = Arrays.copyOf(arr, 10);` |
| `Arrays.equals(arr1, arr2)` | Compare 1D arrays | `Arrays.equals(arr1, arr2);` |
| `Arrays.toString(array)` | Convert 1D array to string | `System.out.println(Arrays.toString(arr));` |
| `Arrays.deepEquals(arr1, arr2)` | Compare multidimensional arrays | `Arrays.deepEquals(matrix1, matrix2);` |
| `Arrays.deepToString(array)` | Convert multidimensional array to string | `System.out.println(Arrays.deepToString(matrix));` |

---
