# Java Stream API 

## 1. Why Streams?

### Imperative vs Declarative

```java
// Imperative (how to do it)
for (String n : names) {
    if (n.length() <= 3) shortNames.add(n);
}
// Declarative (what result you want)
List<String> shortNames = names.stream()
    .filter(n -> n.length() <= 3)
    .collect(Collectors.toList());
```
## 2. What is a Stream?

- Sequence of data  
- Functional pipeline  
- Lazy (executed only at terminal operation)  
- Cannot be reused  

---
- [Stream Interface Doc](https://docs.oracle.com/javase/8/docs/api/java/util/stream/Stream.html)


## 3. Creating Streams

```java
list.stream();              // List → Stream
Arrays.stream(arr);        // Array → Stream
Stream.of(1, 2, 3);        // Values → Stream
Files.lines(Path.of(filePath));// File → Stream (lines)
Stream.generate(Math::random); // Infinite random values
Stream.iterate(0, n -> n + 1); // Infinite sequence
```
## 4. Stream Pipeline Example

```java
int sum = nums.stream()
    .filter(n -> n % 2 == 0)
    .map(n -> n * n)
    .reduce(0, Integer::sum);
```
## 5. Intermediate Operations

| Operation | Purpose |
|----------|--------|
| `filter()` | Select elements |
| `map()` | Transform elements |
| `flatMap()` | Flatten streams |
| `distinct()` | Remove duplicates |
| `sorted()` | Sort elements |
| `limit(n)` | Take first n elements |
| `skip(n)` | Skip first n elements |
| `peek()` | Debug |

---

## 6. Terminal Operations

| Operation | Purpose |
|----------|--------|
| `forEach()` | Iterate elements |
| `collect()` | Convert result |
| `reduce()` | Combine values |
| `count()` | Count elements |
| `findFirst()` | First match |
| `anyMatch()` | Any match |
| `allMatch()` | All match |
| `noneMatch()` | No match |

---

## 7. Collectors

```java
Collectors.toList()
Collectors.toSet()
Collectors.toMap()
Collectors.joining()
Collectors.groupingBy()
Collectors.partitioningBy()
```



## Functional Interface

A functional interface is an interface with only **one abstract method**, which can be used with **lambda expressions** or method references.

```java
@FunctionalInterface
interface Printable {
    void print(); // single abstract method
}
```
## Lambda Expressions (Java 8)

Lambda expressions provide a clear and concise way to implement **functional interfaces**.

They let you treat a piece of behavior (a function) as a variable.

```java
(parameters) -> expression
```
## Example: Functional Interface with Lambda

```java
interface MathOperation {
    int operate(int a, int b);
}

MathOperation add = (a, b) -> a + b;

System.out.println(add.operate(5, 3)); // 8
```
## Built-in Functional Interfaces (in the standard library)

| Interface | Example | Meaning |
|----------|--------|---------|
| `Consumer<T>` | `x -> System.out.println(x)` | Takes input → performs action → no return |
| `Function<T, R>` | `x -> x.length()` | Takes input → returns transformed value |
| `Predicate<T>` | `x -> x.length() > 3` | Takes input → returns true/false |
| `Supplier<T>` | `() -> Math.random()` | No input → returns value |

## Method Reference
A **method reference** is a shorter way to write a **lambda expression** when you are only calling an existing method.

```java
Math::abs //  x -> Math.abs(x)
System.out::println // x -> System.out.println(x)
String::length // x -> x.length()
ArrayList::new // () -> new ArrayList<>()
```
```java
List<Integer> nums = Arrays.asList(-1, -2, 3, -4);

List<Integer> result = nums.stream()
        .map(Math::abs)              // x -> Math.abs(x)
        .collect(Collectors.toList());

System.out.println(result); // [1, 2, 3, 4]
```