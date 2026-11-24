# Java Generics – Exercise: Generic Pair

## Part A – Create a Generic Pair Class

Create a generic class named `Pair<T, U>` that stores two values.

**Requirements:**

1. Declare two instance variables:
   - `first` of type `T`
   - `second` of type `U`
2. Create a constructor to initialize both variables.
3. Create `getFirst()` and `getSecond()` methods.
4. Create a `display()` method to print both values.

Complete the class:

```java
class Pair<T, U> {

    // TODO: Declare two instance variables


    // TODO: Create a constructor


    // TODO: Create getFirst()


    // TODO: Create getSecond()


    // TODO: Create display()

}
```

## Part B – Test with Different Data Types

Complete the following `main()` method.

```java
public class Main {
    public static void main(String[] args) {

        // Pair of String and Integer
        Pair<String, Integer> p1 =
            new Pair<>("Alice", 20);

        // Pair of String and Double
        Pair<String, Double> p2 =
            new Pair<>("Laptop", 999.99);

        // Pair of Integer and String
        Pair<Integer, String> p3 =
            new Pair<>(101, "Java Programming");

        // TODO: Display all three pairs


        // TODO: Print the first value of p1


        // TODO: Print the second value of p2

    }
}
```

**Expected Output:**

```text
Alice 20
Laptop 999.99
101 Java Programming

Alice
999.99
```

**Important:** `T` and `U` are independent type parameters. They do not have to be different types. For example, `Pair<Double, Double>` is perfectly valid.
