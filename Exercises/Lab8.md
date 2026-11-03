# Lecture 8 – Polymorphism Coding Exercise

## Exercise 1: Animal System

**Topics:** Inheritance, method overriding, runtime polymorphism, arrays, `instanceof`, downcasting

Create an animal system that stores different types of animals in one array. Each animal makes a different sound and has its own behavior.

### Part 1: Create the Parent Class – Animal

Create a class named `Animal` with the following:

1. Fields:
   - `String name`
   - `int age`

2. Constructor:
   - Initialize `name` and `age`.

3. Methods:
   - `makeSound()` – prints `"Animal makes a sound."`
   - `displayInfo()` – displays the animal's name and age.

### Part 2: Create the Child Class – Dog

Create a class named `Dog` that extends `Animal`.

1. Add a field:
   - `String breed`

2. Create a constructor to initialize `name`, `age`, and `breed`. Use `super()` to call the parent constructor.

3. Override `makeSound()` to print `"Woof! Woof!"`.

4. Create a method named `fetch()` that prints `"The dog is fetching a ball."`.

### Part 3: Create the Child Class – Cat

Create a class named `Cat` that extends `Animal`.

1. Add a field:
   - `String color`

2. Create a constructor to initialize `name`, `age`, and `color`. Use `super()` to call the parent constructor.

3. Override `makeSound()` to print `"Meow! Meow!"`.

4. Create a method named `climb()` that prints `"The cat is climbing a tree."`.

### Part 4: Main Class

Given the following `Main` class:

```java
public class Main {
    public static void main(String[] args) {

        Animal[] animals = {
            new Animal("Animal 1", 5),
            new Dog("Buddy", 3, "Golden Retriever"),
            new Cat("Kitty", 2, "White"),
            new Dog("Max", 4, "German Shepherd"),
            new Cat("Luna", 1, "Black")
        };

        // A. Use a loop to display each animal's information
        //    and make each animal produce its sound.

        // B. Use instanceof to identify Dog and Cat objects.

        // C. Downcast the reference to call:
        //    Dog: fetch()
        //    Cat: climb()

        // D. Count the number of dogs and cats.

        // E. Display the total number of animals, dogs, and cats.
    }
}
```

### Expected Output

```text
Name: Animal 1
Age: 5
Animal makes a sound.

Name: Buddy
Age: 3
Woof! Woof!
The dog is fetching a ball.

Name: Kitty
Age: 2
Meow! Meow!
The cat is climbing a tree.

Name: Max
Age: 4
Woof! Woof!
The dog is fetching a ball.

Name: Luna
Age: 1
Meow! Meow!
The cat is climbing a tree.

Total Animals: 5
Total Dogs: 2
Total Cats: 2
```

### Questions

1. Why can an `Animal` array store `Animal`, `Dog`, and `Cat` objects?
2. When `animals[i].makeSound()` is called, how does Java decide which method to execute?
3. Why can we call `makeSound()` using an `Animal` reference but cannot directly call `fetch()`?
4. Why do we need `instanceof` before downcasting?
5. Do `Dog` and `Cat` objects remain the same objects after downcasting?