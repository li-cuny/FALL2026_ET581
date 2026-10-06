# **Java Class and Objects**

## **Exercise**

### **1. Create a class called `Fruit`**

Add these members:

```java
String name;
String color;
double weight;
```

Add a method:

```java
void showInfo()
```

The method should print the fruit's name, color, and weight.

---

### **2. Create Multiple Fruit Objects**
Create Main.java with `main()` entry point method.

In `main()`, create **5 Fruit objects**:

```java
Fruit fruit1 = new Fruit();

Fruit fruit2 = new Fruit();

Fruit fruit3 = new Fruit();

Fruit fruit4 = new Fruit();

Fruit fruit5 = new Fruit();
```

Give each fruit a different name, color, and weight.

For example:

```text
Fruit 1: Apple, Red, 0.5
Fruit 2: Mango, Yellow, 0.7
Fruit 3: Orange, Orange, 0.4
Fruit 4: Apple, Green, 0.6
Fruit 5: Mango, Green, 0.8
```

---

### **3. Store the Objects in an Array**

Create a `Fruit` array:

```java
Fruit[] fruits = {
    fruit1,
    fruit2,
    fruit3,
    fruit4,
    fruit5
};
```

---

### **4. Call the Method for Each Fruit**

Use a `for` loop to call `showInfo()` for every fruit in the array.

```java
for (int i = 0; i < fruits.length; i++) {
    fruits[i].showInfo();
}
```

Expected output:

```text
Name: Apple
Color: Red
Weight: 0.5

Name: Mango
Color: Yellow
Weight: 0.7

Name: Orange
Color: Orange
Weight: 0.4

Name: Apple
Color: Green
Weight: 0.6

Name: Mango
Color: Green
Weight: 0.8
```
### **5. Pass a Fruit Object to a Method**

In `Main.java` create a method that accepts a `Fruit` object as a parameter.

```java
static void printFruit(Fruit fruit) {

    fruit.showInfo();

}
```

Then, in `main()`, call the method and pass a `Fruit` object:

```java
printFruit(fruit1);
```

You can also pass different Fruit objects:

```java
printFruit(fruit1);
printFruit(fruit2);
printFruit(fruit3);
```

### **Example**

```java
public static void printFruit(Fruit fruit) {

    fruit.showInfo();

}
```

Calling:

```java
printFruit(fruit1);
```

means that the `fruit1` object is passed to the `printFruit()` method.

### 6. Pass two Fruit Object to a Method**

In Main.java create a method called `compareWeight()` that accepts **two `Fruit` objects**:

```java
static void compareWeight(Fruit fruit1, Fruit fruit2)
```

The method should print which fruit is heavier.

For example:

```text
Mango is heavier than Apple
```
### **7. Pass a Fruit Array to a Method**

Create a method called `getApples()` that accepts a `Fruit` array and **returns a new `Fruit` array containing only the apples**.

```java
static Fruit[] getApples(Fruit[] fruits)
```

The method should check each `Fruit` object and return only the objects whose `name` is `"Apple"`.

### **Example**

Call the method in `main()`:

```java
Fruit[] apples = getApples(fruits);
```

Then use a `for` loop to display the returned array:

```java
for (int i = 0; i < apples.length; i++) {
    apples[i].showInfo();
}
```

### **Example**

If the original `fruits` array contains:

```text
Apple
Mango
Orange
Apple
Mango
```

The returned array should contain:

```text
Apple
Apple
```

### **Method Signature**

```java
static Fruit[] getApples(Fruit[] fruits)
```

### Sample output:
```
print Fruit[] apples:

Name: Apple
Color: Red
Weight: 0.5

Name: Apple
Color: Green
Weight: 0.6
```
### **Hint**

You will need to:

1. Count how many Apple objects are in the array.
2. Create a new `Fruit[]` array with that size.
3. Copy only the Apple objects into the new array.
4. Return the new array.
