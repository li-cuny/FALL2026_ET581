# **Product Class 

## **1 — Product Class and Constructors**

Create a class called `Product`.

Add these private member variables:

```java
private String name;
private double price;
```

Create:

* A one-parameter constructor that receives `name`.
* A two-parameter constructor that receives `name` and `price`.

In `main()`:

* Create two `Product` objects using the two constructors.
* Print their information.

---

## **2 — Getters and Setters**

Use the `Product` class from Project 1.

Add getter and setter methods for:

* `name`
* `price`

In `main()`:

* Create a `Product` object.
* Use the setters to change the name and price.
* Use the getters to print the values.

---

## **3 — `toString()`**

Add the following method to the `Product` class:

```java
public String toString()
```

The method should return the product's name and price.

Example:

```text
Name: Apple
Price: 1.50
```

In `main()`:

```java
Product p1 = new Product("Apple", 1.50);

System.out.println(p1);
```

---

## **4 — `equals()`**

Add the following method:

```java
public boolean equals(Product p)
```

The method should return `true` if two products have the same:

* name
* price

Otherwise, return `false`.

Test it in `main()`:

```java
Product p1 = new Product("Apple", 1.50);
Product p2 = new Product("Apple", 1.50);
Product p3 = new Product("Orange", 1.50);

System.out.println(p1.equals(p2));
System.out.println(p1.equals(p3));
```

Expected output:

```text
true
false
```

---

## **5 — `compareTo()`**

Add the following method:

```java
public int compareTo(Product p)
```

Compare the products based on their **price**.

Return the **difference between the two prices**:

```java
return (int)(this.price - p.price);
```

* Negative number → this product is cheaper
* `0` → prices are equal
* Positive number → this product is more expensive

Test it in `main()`:

```java
Product p1 = new Product("Apple", 10.00);
Product p2 = new Product("Orange", 15.00);

System.out.println(p1.compareTo(p2));
System.out.println(p2.compareTo(p1));
```

---

## **6 — Static Variable**

Add a static variable:

```java
static int count;
```

Use it to count how many `Product` objects are created.

In `main()`:

```java
Product p1 = new Product("Apple", 1.50);
Product p2 = new Product("Orange", 2.00);
Product p3 = new Product("Banana", 1.25);

System.out.println(Product.count);
```

Expected output:

```text
3
```

---

## **7 — Array of Objects**

Create an array that can store five `Product` objects:

```java
Product[] products = new Product[5];
```

Create five products and store them in the array.

Print all products using a `for` loop.

Example output:

```text
Name: Apple, Price: 1.50
Name: Orange, Price: 2.00
Name: Banana, Price: 1.25
Name: Mango, Price: 3.00
Name: Grape, Price: 2.50
```

---

## **8 — Method with an Object Array**

Create a method:

```java
static void printProducts(Product[] products)
```

The method should print all products in the array.

In `main()`:

```java
printProducts(products);
```
## **9 — create sortProduct() in main()

Create a method:
```
static void sortProduct(Product[] products)
```
Use Bubble Sort to sort the products by price from lowest to highest.

Use the `compareTo()` method to compare two products.

**Do not use any library sorting methods such as:**
```
Arrays.sort()
```