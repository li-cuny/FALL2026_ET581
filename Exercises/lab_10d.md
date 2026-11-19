# Java Stream API 


## Exercise 1 – Student Management System

**Topics:** `filter()`, `map()`, `sorted()`, `count()`, `max()`, `average()`

### Student.java

```java
class Student {
    private String name;
    private int age;
    private double gpa;

    public Student(String name, int age, double gpa) {
        this.name = name;
        this.age = age;
        this.gpa = gpa;
    }

    public String getName() { return name; }
    public int getAge() { return age; }
    public double getGpa() { return gpa; }

    @Override
    public String toString() {
        return name + " (Age: " + age + ", GPA: " + gpa + ")";
    }
}
```

### Main.java

```java
import java.util.*;
import java.util.stream.*;

public class Main {

    public static void main(String[] args) {

        List<Student> students = Arrays.asList(
            new Student("Alice", 20, 3.8),
            new Student("Bob", 22, 2.9),
            new Student("Charlie", 19, 3.5),
            new Student("David", 23, 3.2),
            new Student("Emma", 21, 3.9),
            new Student("Frank", 20, 2.5),
            new Student("Grace", 22, 3.7)
        );

        System.out.println("High GPA Students:");
        getHighGpaStudents(students).forEach(System.out::println);

        System.out.println("\nStudent Names:");
        getStudentNames(students).forEach(System.out::println);

        System.out.println("\nSorted by GPA:");
        sortByGpa(students).forEach(System.out::println);

        System.out.println("\nTop Student:");
        System.out.println(getTopStudent(students));

        System.out.println("\nAverage GPA:");
        System.out.println(getAverageGpa(students));

        System.out.println("\nCount of Students Older Than 20:");
        System.out.println(countOlderStudents(students));
    }

    // TODO 1: Return students with GPA greater than 3.5

    // TODO 2: Return a List<String> containing student names

    // TODO 3: Sort students by GPA in descending order

    // TODO 4: Find the student with the highest GPA

    // TODO 5: Calculate the average GPA

    // TODO 6: Count students whose age is greater than 20
}
```

---

## Exercise 2 – Online Shopping System

**Topics:** `filter()`, `map()`, `sorted()`, `reduce()`, `max()`

### Product.java

```java
class Product {

    private String name;
    private String category;
    private double price;
    private int quantity;

    public Product(String name, String category,
                   double price, int quantity) {
        this.name = name;
        this.category = category;
        this.price = price;
        this.quantity = quantity;
    }

    public String getName() { return name; }
    public String getCategory() { return category; }
    public double getPrice() { return price; }
    public int getQuantity() { return quantity; }

    @Override
    public String toString() {
        return name + " - $" + price + " (Qty: " + quantity + ")";
    }
}
```

### Main.java

```java
import java.util.*;
import java.util.stream.*;

public class Main {

    public static void main(String[] args) {

        List<Product> products = Arrays.asList(
            new Product("Laptop", "Electronics", 1200, 5),
            new Product("Mouse", "Electronics", 25, 20),
            new Product("Keyboard", "Electronics", 75, 10),
            new Product("Apple", "Food", 2, 100),
            new Product("Milk", "Food", 4, 50),
            new Product("Desk", "Furniture", 300, 3),
            new Product("Chair", "Furniture", 150, 8)
        );

        System.out.println("Expensive Products:");
        getExpensiveProducts(products).forEach(System.out::println);

        System.out.println("\nElectronics Products:");
        getElectronics(products).forEach(System.out::println);

        System.out.println("\nProduct Names:");
        getProductNames(products).forEach(System.out::println);

        System.out.println("\nMost Expensive Product:");
        System.out.println(getMostExpensive(products));

        System.out.println("\nTotal Inventory Value:");
        System.out.println(getInventoryValue(products));

        System.out.println("\nProducts Sorted by Price:");
        sortByPrice(products).forEach(System.out::println);
    }

    // TODO 1: Return products with price greater than $100

    // TODO 2: Return products belonging to the Electronics category

    // TODO 3: Return a list containing product names

    // TODO 4: Find the most expensive product

    // TODO 5: Calculate total inventory value (price * quantity)

    // TODO 6: Sort products by price in ascending order
}
```

---

## Exercise 3 – Employee Management System

**Topics:** `groupingBy()`, `counting()`, `averagingDouble()`, `max()`, `sorted()`

### Employee.java

```java
class Employee {

    private int id;
    private String name;
    private String department;
    private double salary;

    public Employee(int id, String name,
                    String department, double salary) {
        this.id = id;
        this.name = name;
        this.department = department;
        this.salary = salary;
    }

    public String getName() { return name; }
    public String getDepartment() { return department; }
    public double getSalary() { return salary; }

    @Override
    public String toString() {
        return name + " - " + department + " - $" + salary;
    }
}
```

### Main.java

```java
import java.util.*;
import java.util.stream.*;

public class Main {

    public static void main(String[] args) {

        List<Employee> employees = Arrays.asList(
            new Employee(1, "Alice", "IT", 80000),
            new Employee(2, "Bob", "HR", 55000),
            new Employee(3, "Charlie", "IT", 95000),
            new Employee(4, "David", "Finance", 75000),
            new Employee(5, "Emma", "HR", 65000),
            new Employee(6, "Frank", "Finance", 85000),
            new Employee(7, "Grace", "IT", 90000)
        );

        System.out.println("IT Employees:");
        getITEmployees(employees).forEach(System.out::println);

        System.out.println("\nEmployee Count by Department:");
        System.out.println(countByDepartment(employees));

        System.out.println("\nAverage Salary by Department:");
        System.out.println(averageSalaryByDepartment(employees));

        System.out.println("\nHighest Paid Employee:");
        System.out.println(getHighestPaidEmployee(employees));

        System.out.println("\nEmployees Sorted by Salary:");
        sortBySalary(employees).forEach(System.out::println);
    }

    // TODO 1: Return employees in the IT department

    // TODO 2: Count employees in each department

    // TODO 3: Calculate average salary for each department

    // TODO 4: Find the employee with the highest salary

    // TODO 5: Sort employees by salary in descending order
}
```
