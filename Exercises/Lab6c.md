# Java Class and Objects

## Question 1: Constructor Chaining

Create a class named `Animal` with the following instance variables:

```java
String name;
String type;
int age;
double weight;
```

Requirements:

1. Create a no-argument constructor that uses `this()` to call the four-parameter constructor.
2. Create a four-parameter constructor to initialize all instance variables.
3. Create a `displayInfo()` method to display the animal's information.
4. Use `"Unknown"`, `"Unknown"`, `0`, and `0.0` as the default values.

**Main class:**

```java
public class Main {
    public static void main(String[] args) {
        Animal a1 = new Animal();
        Animal a2 = new Animal("Lion", "Mammal", 5, 190.5);

        a1.displayInfo();
        a2.displayInfo();
    }
}
```

## Question 2: Named and Anonymous Objects

Create a class named `Animal` with the instance variables `name` and `age`.

Requirements:

1. Create a constructor to initialize both variables.
2. Create a `displayInfo()` method.
3. Create a named object with the name `"Tiger"` and age `4`.
4. Use the named object to call `displayInfo()`.
5. Create another animal using an anonymous object and call `displayInfo()` directly without storing the object in a reference variable.

**Main class:**

```java
public class Main {
    public static void main(String[] args) {
        Animal a1 = new Animal("Tiger", 4);

        a1.displayInfo();

        new Animal("Elephant", 10).displayInfo();
    }
}
```

## Question 3: Static Block

Create a class named `Animal` with the following members:

```java
String name;
static String zooName;
```

Requirements:

1. Create a static initialization block that assigns `"Wildlife Zoo"` to `zooName`.
2. Create a constructor that initializes `name`.
3. Create a `displayInfo()` method that prints the animal's name and zoo name.
4. Observe when the static block executes.

**Main class:**

```java
public class Main {
    public static void main(String[] args) {
        Animal a1 = new Animal("Lion");
        Animal a2 = new Animal("Tiger");

        a1.displayInfo();
        a2.displayInfo();
    }
}
```

## Question 4: Instance Initialization Block

Create a class named `Animal` with the instance variable `name`.

Requirements:

1. Create an instance initialization block that prints `"Animal initialization block"`.
2. Create a constructor that initializes `name` and prints `"Animal constructor"`.
3. Create a `displayInfo()` method.
4. Explain how many times the initialization block executes.

**Main class:**

```java
public class Main {
    public static void main(String[] args) {
        Animal a1 = new Animal("Lion");
        Animal a2 = new Animal("Tiger");
        Animal a3 = new Animal("Eagle");

        a1.displayInfo();
        a2.displayInfo();
        a3.displayInfo();
    }
}
```

## Question 5: Static Variable

Create a class named `Animal` with the following members:

```java
String name;
static int count = 0;
```

Requirements:

1. Create a constructor that initializes `name` and increases `count` by one.
2. Create a static method named `displayCount()` that prints the total number of animals created.
3. Explain why `count` is shared by all objects.

**Main class:**

```java
public class Main {
    public static void main(String[] args) {
        Animal a1 = new Animal("Lion");
        Animal a2 = new Animal("Tiger");
        Animal a3 = new Animal("Elephant");
        Animal a4 = new Animal("Giraffe");

        Animal.displayCount();
    }
}
```

## Question 6: Array of Objects

Create a class named `Animal` with the instance variables `name`, `type`, and `age`.

Requirements:

1. Create a constructor to initialize all three variables.
2. Create a `displayInfo()` method.
3. Create an array of five `Animal` objects using the following information.
4. Use a `for` loop to display all five animals.

| Name | Type | Age |
|---|---|---:|
| Lion | Mammal | 5 |
| Eagle | Bird | 3 |
| Turtle | Reptile | 20 |
| Dolphin | Mammal | 8 |
| Parrot | Bird | 4 |

**Main class:**

```java
public class Main {
    public static void main(String[] args) {
        Animal[] animals = {
            new Animal("Lion", "Mammal", 5),
            new Animal("Eagle", "Bird", 3),
            new Animal("Turtle", "Reptile", 20),
            new Animal("Dolphin", "Mammal", 8),
            new Animal("Parrot", "Bird", 4)
        };

        for (int i = 0; i < animals.length; i++) {
            animals[i].displayInfo();
        }
    }
}
```

## Question 7: Passing an Array to a Method

Use the `Animal` class from Question 6.

Requirements:

1. Create a static method named `printAnimals(Animal[] animals)`.
2. Use a `for` loop inside the method to display every animal's information.
3. Create an array of three animals in the `main()` method.
4. Pass the array to `printAnimals()`.

**Main class:**

```java
public class Main {
    public static void main(String[] args) {
        Animal[] animals = {
            new Animal("Lion", "Mammal", 5),
            new Animal("Eagle", "Bird", 3),
            new Animal("Turtle", "Reptile", 20)
        };

        Animal.printAnimals(animals);
    }
}
```

## Question 8: Return an Array of Animals

Create a class named `Animal` with the instance variables `name` and `age`.

Requirements:

1. Create a constructor to initialize both variables.
2. Create a static method named `filterAnimals(Animal[] animals)` that returns an `Animal[]` array.
3. Return only the animals whose ages are greater than or equal to `5`.
4. In the `main()` method, create an array of five animals with different ages.
5. Call `filterAnimals()` and store the returned array in another `Animal[]` variable.
6. Use a `for` loop to display the animals in the returned array.

You may use an `ArrayList` inside the method to collect matching animals, then convert it to an `Animal[]` array before returning it.

**Main class:**

```java
public class Main {
    public static void main(String[] args) {
        Animal[] animals = {
            new Animal("Lion", 5),
            new Animal("Eagle", 3),
            new Animal("Turtle", 20),
            new Animal("Dolphin", 8),
            new Animal("Parrot", 4)
        };

        Animal[] result = Animal.filterAnimals(animals);

        for (int i = 0; i < result.length; i++) {
            result[i].displayInfo();
        }
    }
}
```

---


### Question 9: Static Nested Class

Create a class named `Animal` with the following members:

```java
String name;
static String zooName = "Wildlife Zoo";
```

Requirements:

1. Create a constructor to initialize `name`.
2. Create a static nested class named `ZooInfo`.
3. Add a method named `displayZooName()` inside `ZooInfo`.
4. Display the static variable `zooName` inside the method.
5. Explain why the static nested class can access `zooName` directly but cannot access an individual animal's `name` directly.

**Main class:**

```java
public class Main {
    public static void main(String[] args) {
        Animal.ZooInfo info = new Animal.ZooInfo();

        info.displayZooName();
    }
}
```

### Question 10: Inner Class

Create a class named `Animal` with the instance variable `name`.

Requirements:

1. Create a constructor to initialize `name`.
2. Create a non-static inner class named `Sound`.
3. Add a method named `makeSound()` inside `Sound` that prints the animal's name followed by `" makes a sound."`.
4. Explain how the inner class accesses the outer object's `name`.

**Main class:**

```java
public class Main {
    public static void main(String[] args) {
        Animal a1 = new Animal("Lion");

        Animal.Sound sound = a1.new Sound();

        sound.makeSound();
    }
}
```
