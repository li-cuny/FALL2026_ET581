# Lecture 8 – Polymorphism Coding Exercise

## Exercise 1: Animal Management System


### Part 1: Create the Parent Class – Animal

Create a class named `Animal` with the following:

1. **Fields:**
   - `String name`
   - `int age`
   - `double weight`

2. **Constructor:**
   - Initialize all three fields.

3. **Methods:**
   - `makeSound()` – prints `"Animal makes a sound."`
   - `displayInfo()` – displays the animal's name, age, and weight.

### Part 2: Create the Child Class – Dog

Create a class named `Dog` that extends `Animal`.

1. Add a field:
   - `String breed`

2. Create a constructor to initialize `name`, `age`, `weight`, and `breed`.
   - Use `super()` to call the parent constructor.

3. Override `makeSound()` to print `"Woof! Woof!"`.

4. Create a method named `fetch()` that prints `"The dog is fetching a ball."`.

### Part 3: Create the Child Class – Cat

Create a class named `Cat` that extends `Animal`.

1. Add a field:
   - `String color`

2. Create a constructor to initialize `name`, `age`, `weight`, and `color`.
   - Use `super()` to call the parent constructor.

3. Override `makeSound()` to print `"Meow! Meow!"`.

4. Create a method named `climb()` that prints `"The cat is climbing a tree."`.

---

### Part 4: Main Class

Given the following `Main` class:

```java
public class Main {
    public static void main(String[] args) {

        Animal[] animals = {
            new Animal("Animal1", 6, 15.0),
            new Dog("Buddy", 3, 25.5, "Golden Retriever"),
            new Cat("Kitty", 2, 4.5, "White"),
            new Dog("Max", 5, 30.0, "German Shepherd"),
            new Cat("Luna", 4, 5.2, "Black"),
            new Dog("Rocky", 2, 18.5, "Poodle"),
            new Cat("Milo", 1, 3.8, "Gray"),
            new Dog("Charlie", 7, 28.0, "Bulldog")
        };

        // Complete Tasks A–M below.
    }
}
```

---

### Part 5: Basic Polymorphism Tasks

**A. Display All Animals**

Use an enhanced for loop to:
- Display each animal's information.
- Call `makeSound()`.

**B. Identify Animal Types**

Use a loop to go through all objects in the `animals` array.

Use `instanceof` to identify each object:
- If it is a `Dog`, display `"Dog"`.
- If it is a `Cat`, display `"Cat"`.
- Otherwise, display `"regular Animal"`.

**C. Call Subclass Methods**

Use a loop, `instanceof`, and downcasting to call the appropriate method:
- Dog: `fetch()`
- Cat: `climb()`

**D. Count Animal Types**

Count and display:
- Total number of animals.
- Number of dogs.
- Number of cats.

Use `instanceof`.

---

### Part 6: Advanced Array Tasks

**E. Find the Oldest Animal**

Find and display the animal with the greatest age.

Do not assume the first animal is the oldest.

**F. Find the Heaviest Dog**

Find and display the dog with the greatest weight.

Use `instanceof` and downcasting to identify dogs.

**G. Calculate Average Weight**

Calculate and display:
- Average weight of all animals.
- Average weight of dogs.
- Average weight of cats.

**H. Search by Name**

Search for an animal using the following name:

```java
String searchName = "Luna";
```

Display the animal's complete information if found. Otherwise, display `"Animal not found."`.

**I. Display Animals Above a Given Age**

Display all animals whose age is greater than 3.

**J. Find the Second Heaviest Animal**

Find and display the animal with the second greatest weight.

Assume all animals have different weights.

**K. Separate Dogs and Cats into Two Arrays**

Create two arrays:

```java
Dog[] dogs;
Cat[] cats;
```

Requirements:
- Count the number of dogs and cats first.
- Create arrays with the correct sizes.
- Store the corresponding objects from the original `animals` array.
- Do not create new Dog or Cat objects. Reuse the existing objects.

**L. Display the Two Arrays**

Use enhanced for loops to display all dogs and cats separately.

**M. Sort Animals by Weight**

Sort the original `animals` array in ascending order by weight.

Requirements:
- Do not use `Arrays.sort()`.
- Use nested loops.
- Swap object references when necessary.
- Display the sorted animals.

---

### Part 7: Concept Questions

1. Why can an `Animal` array store `Animal`, `Dog`, and `Cat` objects?
2. When `animals[i].makeSound()` is called, how does Java decide which method to execute?
3. Why can we call `makeSound()` using an `Animal` reference but cannot directly call `fetch()`?
4. Why do we need `instanceof` before downcasting?
5. Do `Dog` and `Cat` objects remain the same objects after downcasting?
6. When sorting the `animals` array, are we swapping the actual objects or the references?
7. Why can we store a `Dog` object in a `Dog[]` array after retrieving it from an `Animal[]` array?

---

### Important Requirements

- Use inheritance instead of repeating fields and methods.
- Use `super()` in the child constructors.
- Use `@Override` when overriding methods.
- Use loops to process arrays.
- Use `instanceof` before downcasting.
- Do not use `Arrays.sort()` or `ArrayList`.
- Do not create duplicate animal objects when separating the arrays.

---

# Sample Output

The following outputs are based on the original `animals` array.

## A. Display All Animals

```text
Name: Animal1
Age: 6
Weight: 15.0
Animal makes a sound.

Name: Buddy
Age: 3
Weight: 25.5
Woof! Woof!

Name: Kitty
Age: 2
Weight: 4.5
Meow! Meow!

Name: Max
Age: 5
Weight: 30.0
Woof! Woof!

Name: Luna
Age: 4
Weight: 5.2
Meow! Meow!

Name: Rocky
Age: 2
Weight: 18.5
Woof! Woof!

Name: Milo
Age: 1
Weight: 3.8
Meow! Meow!

Name: Charlie
Age: 7
Weight: 28.0
Woof! Woof!
```

## B. Identify Animal Types

```text
Animal1 is a regular Animal.
Buddy is a Dog.
Kitty is a Cat.
Max is a Dog.
Luna is a Cat.
Rocky is a Dog.
Milo is a Cat.
Charlie is a Dog.
```

## C. Call Subclass Methods

```text
Buddy:
The dog is fetching a ball.

Kitty:
The cat is climbing a tree.

Max:
The dog is fetching a ball.

Luna:
The cat is climbing a tree.

Rocky:
The dog is fetching a ball.

Milo:
The cat is climbing a tree.

Charlie:
The dog is fetching a ball.
```

## D. Count Animal Types

```text
Total Animals: 8
Total Dogs: 4
Total Cats: 3
```

## E. Find the Oldest Animal

```text
Oldest Animal:
Name: Charlie
Age: 7
Weight: 28.0
```

## F. Find the Heaviest Dog

```text
Heaviest Dog:
Name: Max
Age: 5
Weight: 30.0
```

## G. Calculate Average Weight

```text
Average Weight of All Animals: 16.3125
Average Weight of Dogs: 25.5
Average Weight of Cats: 4.5
```

## H. Search by Name

```text
Searching for: Luna

Animal Found!
Name: Luna
Age: 4
Weight: 5.2
```

## I. Display Animals Above a Given Age

```text
Animals Older Than 3:

Animal1 - Age: 6
Max - Age: 5
Luna - Age: 4
Charlie - Age: 7
```

## J. Find the Second Heaviest Animal

```text
Second Heaviest Animal:
Name: Charlie
Age: 7
Weight: 28.0
```

## K. Separate Dogs and Cats into Two Arrays

```text
Dog Array Size: 4
Cat Array Size: 3
```

## L. Display the Two Arrays

```text
Dogs:

Name: Buddy
Age: 3
Weight: 25.5

Name: Max
Age: 5
Weight: 30.0

Name: Rocky
Age: 2
Weight: 18.5

Name: Charlie
Age: 7
Weight: 28.0


Cats:

Name: Kitty
Age: 2
Weight: 4.5

Name: Luna
Age: 4
Weight: 5.2

Name: Milo
Age: 1
Weight: 3.8
```

## M. Sort Animals by Weight

```text
Animals Sorted by Weight (Ascending):

Milo - 3.8
Kitty - 4.5
Luna - 5.2
Animal1 - 15.0
Rocky - 18.5
Buddy - 25.5
Charlie - 28.0
Max - 30.0
```