# Lab 7: Java Packages and Access Modifiers

## Exercise: School Records Access Challenge

### Objective

In this exercise, you will create Java classes in different packages and test how the `public`, `private`, and default access modifiers work.

You will learn how to:

- Create Java packages.
- Access fields from classes in the same package.
- Import and use a class from a different package.
- Identify compilation errors caused by access modifiers.
- Use a public getter method to access a private field.
- Compile and run Java programs using `javac` and `java -cp`.

## Step 1: Create the Project Structure

Create a project folder named `Lab7`.

Inside `Lab7`, create the following folders and files:

```text
Lab7/
├── src/
│   └── edu/
│       └── school/
│           ├── SchoolRecord.java
│           ├── SchoolTest.java
│           └── visitors/
│               └── VisitorTest.java
└── bin/
```

**Important:**

- Save all Java source files inside the correct folders.
- The `src` folder contains your `.java` files.
- The `bin` folder will contain compiled `.class` files.
- The package declaration must match the folder structure.

## Step 2: Create `SchoolRecord.java`

**File location:** `src/edu/school/SchoolRecord.java`

This class stores information about a school.

Copy the following code:

```java
package edu.school;

public class SchoolRecord {
    public String schoolName = "Central School";
    private double tuition = 1200.50;
    String studentName = "Alice"; // default access
}
```

### Understand the code

1. `schoolName` uses `public` access. It can be accessed from other classes, including classes in different packages, provided the class itself is accessible.
2. `tuition` uses `private` access. It can only be accessed directly inside `SchoolRecord`.
3. `studentName` uses default access because no modifier is written. It can be accessed by classes in the same package.

Do not add a `main()` method to this file. You will run the other two classes to test access.

## Step 3: Create `SchoolTest.java`

**File location:** `src/edu/school/SchoolTest.java`

This class is in the same package as `SchoolRecord`.

### Instructions

1. Declare the package `edu.school`.
2. Create a public class named `SchoolTest`.
3. Add the `main()` method.
4. Create a `SchoolRecord` object.
5. Try to print all three fields.

Start with this code:

```java
package edu.school;

public class SchoolTest {
    public static void main(String[] args) {
        SchoolRecord record = new SchoolRecord();

        System.out.println(record.schoolName);
        System.out.println(record.tuition);
        System.out.println(record.studentName);
    }
}
```

### Test your program

The line accessing `record.tuition` causes a compilation error because `tuition` is private.

**Task:**

1. Comment out the line that accesses `record.tuition`.
2. Compile and run the program again.
3. Observe the output.

Use this command from the `Lab7` project directory:

```bash
javac -d bin src/edu/school/SchoolRecord.java src/edu/school/SchoolTest.java
```

Run the program:

```bash
java -cp bin edu.school.SchoolTest
```

**Expected output:**

```text
Central School
Alice
```

### Questions

1. Why can `SchoolTest` access `schoolName`?
2. Why can `SchoolTest` access `studentName`?
3. Why can `SchoolTest` not access `tuition` directly, even though both classes are in the same package?

Write your answers:

1. __________________________________________________

2. __________________________________________________

3. __________________________________________________

## Step 4: Create `VisitorTest.java`

**File location:** `src/edu/school/visitors/VisitorTest.java`

This class belongs to a different package: `edu.school.visitors`.

### Instructions

1. Declare the package `edu.school.visitors`.
2. Import `edu.school.SchoolRecord`.
3. Create a public class named `VisitorTest`.
4. Add the `main()` method.
5. Create a `SchoolRecord` object.
6. Try to print all three fields.

Start with this code:

```java
package edu.school.visitors;

import edu.school.SchoolRecord;

public class VisitorTest {
    public static void main(String[] args) {
        SchoolRecord record = new SchoolRecord();

        System.out.println(record.schoolName);
        System.out.println(record.tuition);
        System.out.println(record.studentName);
    }
}
```

### Test your program

Compile all source files from the `Lab7` project directory:

```bash
javac -d bin $(find src -name "*.java")
```

You should see compilation errors for the lines accessing `tuition` and `studentName`.

**Task:**

1. Identify which lines cause compilation errors.
2. Write a comment explaining why each line fails.
3. Comment out both invalid lines.
4. Compile and run the program again.

Run:

```bash
java -cp bin edu.school.visitors.VisitorTest
```

**Expected output:**

```text
Central School
```

### Questions

1. Why can `VisitorTest` access `schoolName`?
2. Why can it not access `studentName`?
3. Why can it not access `tuition`?
4. Are `edu.school` and `edu.school.visitors` the same package? Explain.

Write your answers:

1. __________________________________________________

2. __________________________________________________

3. __________________________________________________

4. __________________________________________________

## Step 5: Fix the Private Access Problem

A private field cannot be accessed directly outside its class. However, the class can provide a public method that returns its value.

### Task A: Modify `SchoolRecord.java`

Add the following method inside the `SchoolRecord` class, below the existing fields:

```java
public double getTuition() {
    return tuition;
}
```

Your `SchoolRecord.java` should now contain:

```java
package edu.school;

public class SchoolRecord {
    public String schoolName = "Central School";
    private double tuition = 1200.50;
    String studentName = "Alice"; // default access

    public double getTuition() {
        return tuition;
    }
}
```

### Task B: Modify `VisitorTest.java`

Inside the `main()` method, add:

```java
System.out.println(record.getTuition());
```

Keep the lines accessing `record.tuition` and `record.studentName` commented out.

Your corrected `main()` method should look like this:

```java
public static void main(String[] args) {
    SchoolRecord record = new SchoolRecord();

    System.out.println(record.schoolName);
    // System.out.println(record.tuition);
    // System.out.println(record.studentName);

    System.out.println(record.getTuition());
}
```

### Task C: Compile and run again

From the `Lab7` project directory, compile all Java files:

```bash
javac -d bin $(find src -name "*.java")
```

Run:

```bash
java -cp bin edu.school.visitors.VisitorTest
```

**Expected output:**

```text
Central School
1200.5
```

### Questions

1. Why can `VisitorTest` call `getTuition()`?
2. Does the getter make the `tuition` field public?
3. Why is using a getter useful?

Write your answers:

1. __________________________________________________

2. __________________________________________________

3. __________________________________________________

## Step 6: Complete the Results Table

Complete the table based on your testing.

| Member | Same package | Different package |
|---|---|---|
| `schoolName` (`public`) | __________ | __________ |
| `tuition` (`private`) | __________ | __________ |
| `studentName` (default) | __________ | __________ |
| `getTuition()` (`public`) | __________ | __________ |

Use **Accessible** or **Not accessible** for each answer.



