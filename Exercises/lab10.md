# Java Collection Frameworks -- Coding Exercises

These exercises provide practice with the Java Collections Framework,
including `Collection`, `List`, `ArrayList`, `Iterator`, and
`ListIterator`.

------------------------------------------------------------------------

## Exercise 1 -- Basic Collection Operations

**Topics:** `Collection`, `ArrayList`, `add()`, `remove()`,
`contains()`, `size()`, `isEmpty()`

### Description

Write a Java program to manage a collection of student names.

### Requirements

1.  Create a `Collection<String>` named `students` using an `ArrayList`.
2.  Add the following names:
    -   Alice
    -   Bob
    -   Charlie
    -   David
3.  Display all student names.
4.  Check whether `"Bob"` exists in the collection.
5.  Remove `"Charlie"` from the collection.
6.  Display the total number of students.
7.  Check whether the collection is empty.

### Given Main Method

``` java
import java.util.*;

public class Exercise1 {
    public static void main(String[] args) {

        // TODO 1: Create a Collection<String> named students.

        // TODO 2: Add four student names.

        // TODO 3: Display all students.

        // TODO 4: Check whether "Bob" exists.

        // TODO 5: Remove "Charlie".

        // TODO 6: Display the collection size.

        // TODO 7: Check whether the collection is empty.

    }
}
```

------------------------------------------------------------------------

## Exercise 2 -- ArrayList and Index-Based Operations

**Topics:** `List`, `ArrayList`, `get()`, `set()`,
`add(index, element)`, `remove(index)`, `indexOf()`

### Description

Write a Java program to manage a shopping list.

### Requirements

1.  Create a `List<String>` named `shoppingList`.
2.  Add the following items:
    -   Milk
    -   Bread
    -   Eggs
    -   Apple
3.  Display the second item.
4.  Insert `"Orange"` at index 1.
5.  Replace `"Eggs"` with `"Cheese"`.
6.  Remove the item at index 0.
7.  Display the index of `"Apple"`.
8.  Display the final shopping list.

### Given Main Method

``` java
import java.util.*;

public class Exercise2 {
    public static void main(String[] args) {

        // TODO 1: Create the shopping list.

        // TODO 2: Add four items.

        // TODO 3: Display the second item.

        // TODO 4: Insert Orange at index 1.

        // TODO 5: Replace Eggs with Cheese.

        // TODO 6: Remove the first item.

        // TODO 7: Find the index of Apple.

        // TODO 8: Display the final list.

    }
}
```

------------------------------------------------------------------------

## Exercise 3 -- Iterator: Display and Remove Elements

**Topics:** `Iterator`, `hasNext()`, `next()`, `remove()`

### Description

Write a Java program to process a collection of numbers.

### Requirements

1.  Create a `Collection<Integer>` named `numbers` using an `ArrayList`.

2.  Add the following numbers:

    `10, 15, 20, 25, 30, 35, 40`

3.  Use an `Iterator` to display all numbers.

4.  Use another `Iterator` to remove all numbers divisible by 10.

5.  Display the remaining numbers.

6.  Display the final collection size.

### Given Main Method

``` java
import java.util.*;

public class Exercise3 {
    public static void main(String[] args) {

        Collection<Integer> numbers = new ArrayList<>();

        // TODO 1: Add the numbers.

        // TODO 2: Create an Iterator.
        // Display all numbers using while and hasNext().

        // TODO 3: Create another Iterator.
        // Remove numbers divisible by 10.
        // Use Iterator's remove() method.

        // TODO 4: Display the remaining numbers.

        // TODO 5: Display the collection size.

    }
}
```

**Important:** Use `Iterator.remove()` to remove elements while
iterating. Do not call `numbers.remove()` inside the iteration loop.

------------------------------------------------------------------------

## Exercise 4 -- ListIterator: Forward and Backward Traversal

**Topics:** `ListIterator`, `hasNext()`, `next()`, `hasPrevious()`,
`previous()`, `nextIndex()`, `previousIndex()`

### Description

Write a Java program to manage a list of programming languages.

### Requirements

1.  Create a `List<String>` named `languages`.
2.  Add the following languages:
    -   Java
    -   Python
    -   C++
    -   JavaScript
3.  Create a `ListIterator<String>`.
4.  Traverse the list from beginning to end and display each language.
5.  Display the list again from end to beginning.
6.  Display the index of the next element before each call to `next()`.
7.  Display the index of the previous element before each call to
    `previous()`.

### Given Main Method

``` java
import java.util.*;

public class Exercise4 {
    public static void main(String[] args) {

        List<String> languages = new ArrayList<>();

        languages.add("Java");
        languages.add("Python");
        languages.add("C++");
        languages.add("JavaScript");

        ListIterator<String> it = languages.listIterator();

        // TODO 1: Traverse forward.
        // Display the next index and element.

        System.out.println("\\nBackward:");

        // TODO 2: Traverse backward.
        // Display the previous index and element.

    }
}
```

------------------------------------------------------------------------

## Exercise 5 -- ListIterator: Modify Elements While Iterating

**Topics:** `ListIterator`, `add()`, `set()`, `remove()`

### Description

Write a Java program to update a list of student names.

### Requirements

1.  Create a `List<String>` named `students`.

2.  Add the following names:

    `Alice, Bob, Charlie, David, Eric`

3.  Use a `ListIterator` to traverse the list.

4.  If the name is `"Bob"`, replace it with `"Robert"` using `set()`.

5.  If the name is `"Charlie"`, remove it using `remove()`.

6.  When the iterator reaches `"David"`, insert `"Frank"` immediately
    after `"David"` using `add()`.

7.  Display the final list.

### Given Main Method

``` java
import java.util.*;

public class Exercise5 {
    public static void main(String[] args) {

        List<String> students = new ArrayList<>();

        students.add("Alice");
        students.add("Bob");
        students.add("Charlie");
        students.add("David");
        students.add("Eric");

        ListIterator<String> it = students.listIterator();

        while (it.hasNext()) {

            String name = it.next();

            // TODO 1: Replace Bob with Robert.

            // TODO 2: Remove Charlie.

            // TODO 3: Insert Frank after David.

        }

        // TODO 4: Display the final list.

    }
}
```

**Important:** `set()`, `add()`, and `remove()` operate on the
iterator's current position. The order of operations matters.

------------------------------------------------------------------------

## Exercise 6 -- Student Grade Management System

**Topics:** `Collection`, `List`, `Iterator`, `ListIterator`, `add()`,
`remove()`, `contains()`, `set()`, `addAll()`, `retainAll()`

### Description

Create a student grade management program using Java Collections.

### Requirements

#### Part A -- Create Student Lists

1.  Create two `List<String>` objects:

    -   `students`
    -   `passedStudents`

2.  Add the following students to `students`:

    `Alice, Bob, Charlie, David, Eric, Frank`

3.  Add the following students to `passedStudents`:

    `Alice, Charlie, Eric`

#### Part B -- Collection Operations

4.  Display all students.
5.  Check whether `"David"` exists in the student list.
6.  Display the total number of students.
7.  Create another list named `allPassedStudents`, initially containing
    `"George"`.
8.  Use `addAll()` to add all students from `passedStudents` to
    `allPassedStudents`.

#### Part C -- Iterator

9.  Use an `Iterator` to remove students whose names start with `"D"` or
    `"F"` from the original `students` list.
10. Display the remaining students.

#### Part D -- ListIterator

11. Use a `ListIterator` to traverse the remaining student list.
12. Replace `"Bob"` with `"Robert"` using `set()`.
13. Insert `"Henry"` immediately after `"Eric"` using `add()`.
14. Display the final student list.

#### Part E -- Bulk Operations

15. Create a new list containing only students who are also in
    `passedStudents`, using `retainAll()`.
16. Display the final passed student list.

### Given Main Method

``` java
import java.util.*;

public class Exercise6 {
    public static void main(String[] args) {

        List<String> students = new ArrayList<>();
        List<String> passedStudents = new ArrayList<>();

        // TODO 1: Add six students to students.

        // TODO 2: Add three students to passedStudents.

        // TODO 3: Display all students.

        // TODO 4: Check whether David exists.

        // TODO 5: Display the number of students.

        // TODO 6: Create allPassedStudents.
        // Initially add George.
        // Use addAll() to add passedStudents.

        // TODO 7: Use Iterator to remove names
        // starting with D or F.

        // TODO 8: Display the remaining students.

        // TODO 9: Use ListIterator to replace Bob
        // with Robert.

        // TODO 10: Insert Henry after Eric.

        // TODO 11: Display the final student list.

        // TODO 12: Create a new list containing
        // only students who passed.
        // Use retainAll().

        // TODO 13: Display the final passed student list.

    }
}
```

------------------------------------------------------------------------

# Sample Output

The following output shows the expected results for each exercise.

## Exercise 1

``` text
Students: [Alice, Bob, Charlie, David]
Contains Bob: true
After removing Charlie: [Alice, Bob, David]
Number of students: 3
Is empty: false
```

## Exercise 2

``` text
Second item: Bread
Final list: [Orange, Bread, Cheese, Apple]
Index of Apple: 3
```

## Exercise 3

``` text
Original numbers:
10 15 20 25 30 35 40

Remaining numbers:
[15, 25, 35]
Collection size: 3
```

## Exercise 4

``` text
Forward:
0 Java
1 Python
2 C++
3 JavaScript

Backward:
3 JavaScript
2 C++
1 Python
0 Java
```

## Exercise 5

``` text
Final list:
[Alice, Robert, David, Frank, Eric]
```

## Exercise 6

``` text
All students:
[Alice, Bob, Charlie, David, Eric, Frank]

Contains David: true
Number of students: 6

All passed students:
[George, Alice, Charlie, Eric]

After Iterator removal:
[Alice, Bob, Charlie, Eric]

Final student list:
[Alice, Robert, Charlie, Eric, Henry]

Passed students:
[Alice, Charlie, Eric]
```
