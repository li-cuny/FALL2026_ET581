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
