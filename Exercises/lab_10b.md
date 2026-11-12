# Java Coding Exercises – Set, Queue, and Sorting

## Problem 1 – Find Duplicate Numbers

**Concepts:** `HashSet`, `add()`, duplicate detection

Given an array of integers, write a Java program to find and display all duplicate numbers.

**Requirements:**

1. Create an integer array containing:

   `10, 20, 30, 20, 40, 10, 50`

2. Create a `HashSet<Integer>` to keep track of numbers that have already been visited.
3. Use a loop to check each number in the array.
4. If a number has already been added to the Set, display it as a duplicate.
5. Otherwise, add it to the Set.

**Starter Code:**

```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        int[] numbers = {10, 20, 30, 20, 40, 10, 50};

        HashSet<Integer> seen = new HashSet<>();

        // TODO: Find and display duplicate numbers.

    }
}
```

**Expected Output:**

```text
Duplicate numbers: 20 10
```

---

## Problem 2 – Customer Service Queue

**Concepts:** `Queue`, `offer()`, `poll()`, `peek()`

A bank serves customers in the order they arrive.

Write a Java program to manage the customer service queue.

**Requirements:**

1. Create a `Queue<String>` using `LinkedList`.
2. Add the following customers using `offer()`:
   - Alice
   - Bob
   - Charlie
   - David
3. Display the queue.
4. Display the next customer using `peek()`.
5. Serve the first two customers using `poll()` and display their names.
6. Display the remaining queue.
7. Display the next customer to be served.

**Starter Code:**

```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        Queue<String> customers = new LinkedList<>();

        // TODO 1: Add four customers to the queue.


        // TODO 2: Display the queue.


        // TODO 3: Display the next customer using peek().


        // TODO 4: Serve the first two customers using poll().
        // Display each customer being served.


        // TODO 5: Display the remaining queue.


        // TODO 6: Display the next customer.

    }
}
```

**Expected Output:**

```text
Customer queue: [Alice, Bob, Charlie, David]
Next customer: Alice
Serving customer: Alice
Serving customer: Bob
Remaining queue: [Charlie, David]
Next customer: Charlie
```

---

## Problem 3 – Sort Numbers

**Concepts:** `ArrayList`, `Collections.sort()`, `Comparator`

Write a Java program to sort a list of integers in ascending and descending order.

**Requirements:**

1. Create an `ArrayList<Integer>` containing:

   `35, 10, 50, 20, 40`

2. Display the original list.
3. Use `Collections.sort()` to sort the numbers in ascending order.
4. Display the sorted list.
5. Use `Collections.sort()` with a `Comparator` to sort the numbers in descending order.
6. Display the list again.

**Starter Code:**

```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        ArrayList<Integer> numbers = new ArrayList<>();

        numbers.add(35);
        numbers.add(10);
        numbers.add(50);
        numbers.add(20);
        numbers.add(40);

        // TODO 1: Display the original list.


        // TODO 2: Sort in ascending order.


        // TODO 3: Display the ascending order list.


        // TODO 4: Sort in descending order using a Comparator.


        // TODO 5: Display the descending order list.

    }
}
```

**Expected Output:**

```text
Original list: [35, 10, 50, 20, 40]
Ascending order: [10, 20, 35, 40, 50]
Descending order: [50, 40, 35, 20, 10]
```

---

## Problem 4 – Sort Students by Age and Name

**Concepts:** Classes, `Comparable`, `Comparator`, `Collections.sort()`

Create a class named `Student` with the following instance variables:

- `String name`
- `int age`

**Requirements:**

1. Implement the `Comparable<Student>` interface.
2. Create a constructor to initialize `name` and `age`.
3. Override `compareTo()` to sort students by age in ascending order.
4. Override `toString()` to display each student's name and age.
5. In the `main()` method:
   - Create an `ArrayList<Student>`.
   - Add the following students:

| Name | Age |
|---|---:|
| Alice | 22 |
| Bob | 20 |
| Charlie | 25 |
| David | 19 |
| Emma | 22 |

   - Display the original list.
   - Use `Collections.sort()` to sort students by age.
   - Display the sorted list.
   - Use `Collections.sort()` with a `Comparator` to sort students by name in alphabetical order.
   - Display the sorted list.

**Starter Code:**

```java
import java.util.*;

class Student implements Comparable<Student> {
    String name;
    int age;

    // TODO 1: Create a constructor.


    // TODO 2: Implement compareTo() to sort by age.


    // TODO 3: Override toString().

}

public class Main {
    public static void main(String[] args) {
        ArrayList<Student> students = new ArrayList<>();

        students.add(new Student("Alice", 22));
        students.add(new Student("Bob", 20));
        students.add(new Student("Charlie", 25));
        students.add(new Student("David", 19));
        students.add(new Student("Emma", 22));

        // TODO 4: Display the original list.


        // TODO 5: Sort students by age using Collections.sort().


        // TODO 6: Display the list sorted by age.


        // TODO 7: Sort students by name using a Comparator.


        // TODO 8: Display the list sorted by name.

    }
}
```

**Expected Output:**

```text
Original list:
[Alice(22), Bob(20), Charlie(25), David(19), Emma(22)]

Sorted by age:
[David(19), Bob(20), Alice(22), Emma(22), Charlie(25)]

Sorted by name:
[Alice(22), Bob(20), Charlie(25), David(19), Emma(22)]
```
