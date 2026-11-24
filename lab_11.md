# Java Generics

## 1. What Are Generics?

Generics allow a class, interface, or method to work with different data types while maintaining **type safety**.

For example, we can create:

```java
Box<String> nameBox = new Box<>();
Box<Integer> ageBox = new Box<>();
Box<Student> studentBox = new Box<>();
```

The same `Box<T>` class can store different types of data.

Let's apply the same idea to a linked list.

---

## 2. Example LinkedList Node

A linked list is made up of individual objects called **nodes**.

Each node contains two parts:

1. `data` – the value stored in the node.
2. `next` – a reference to the next node.

For example:

```text
+------+------+
| data | next | ---->
+------+------+
```

A node does not need to know where the next node is stored in memory. It only needs a reference to it.

---

## 3. Create a Node Without Generics

Suppose we only want to store integers.

```java
class Node {
    int data;
    Node next;

    public Node(int data) {
        this.data = data;
        this.next = null;
    }
}
```

We can connect two nodes:

```java
Node n1 = new Node(10);
Node n2 = new Node(20);

n1.next = n2;

System.out.println(n1.data);       // 10
System.out.println(n1.next.data);  // 20
```

### What if we want to store other data types?

We might create separate classes:

- `IntegerNode`
- `StringNode`
- `StudentNode`

These classes would have almost the same structure. This creates duplicate code.

---

## 4. Create a Generic Node

```java
class Node<T> {
    T data;
    Node<T> next;

    public Node(T data) {
        this.data = data;
        this.next = null;
    }
}
```

### Understand the code

| Code | Meaning |
|---|---|
| `Node<T>` | Defines a generic Node class. |
| `T data` | Stores a value of type `T`. |
| `Node<T> next` | References another node of the same type. |
| `Node(T data)` | Constructor receives a value of type `T`. |

`T` is a type parameter. It is a placeholder for a data type that will be specified when we create a Node.

The letter `T` is a convention. We could use another valid identifier, but `T` is commonly used to mean Type.

---

## 5. Create Nodes With Different Data Types

### Example A: Integer Nodes

```java
Node<Integer> n1 = new Node<>(10);
Node<Integer> n2 = new Node<>(20);

n1.next = n2;

System.out.println(n1.data);
System.out.println(n1.next.data);
```

Output:

```text
10
20
```

### Example B: String Nodes

```java
Node<String> s1 = new Node<>("Alice");
Node<String> s2 = new Node<>("Bob");

s1.next = s2;

System.out.println(s1.data);
System.out.println(s1.next.data);
```

Output:

```text
Alice
Bob
```

### Example C: Student Nodes

Assume we have this `Student` class:

```java
class Student {
    String name;

    public Student(String name) {
        this.name = name;
    }
}
```

We can create nodes that store Student objects:

```java
Node<Student> st1 = new Node<>(new Student("Alice"));
Node<Student> st2 = new Node<>(new Student("Bob"));

st1.next = st2;

System.out.println(st1.data.name);
System.out.println(st1.next.data.name);
```

Output:

```text
Alice
Bob
```

**Important:** `Node<Student>` stores Student objects. The `data` variable is a Student reference, so we can access Student fields and methods through it.

---

## 6. Visualize a Linked List

Consider the following code:

```java
Node<Integer> n1 = new Node<>(10);
Node<Integer> n2 = new Node<>(20);
Node<Integer> n3 = new Node<>(30);

n1.next = n2;
n2.next = n3;
```

The linked list looks like this:

```text
 head
  |
  v
+------+------+
|  10  | next | ---->
+------+------+
                 +------+------+
                 |  20  | next | ---->
                 +------+------+
                                    +------+------+
                                    |  30  | null |
                                    +------+------+
```

Each node stores an integer and a reference to the next node.

The last node's `next` is `null`, which means there is no next node.

### Access the Nodes

```java
System.out.println(n1.data);           // 10
System.out.println(n1.next.data);      // 20
System.out.println(n1.next.next.data); // 30
```

Notice:

- `n1.data` accesses the first node's data.
- `n1.next.data` accesses the second node's data.
- `n1.next.next.data` accesses the third node's data.

---

## 7. Why Is `Node<T> next` Also Generic?

Look at this declaration:

```java
class Node<T> {
    T data;
    Node<T> next;
}
```

Both `data` and `next` use the same type parameter `T`.

For example, when we create:

```java
Node<Integer> n1 = new Node<>(10);
```

The type parameter `T` is replaced with `Integer` for this use of the class.

Conceptually, the fields behave like:

```java
Integer data;
Node<Integer> next;
```

Therefore, an integer node points to another integer node.

Likewise, a `Node<String>` points to another `Node<String>`.

---

## 8. Type Safety

Generics check types at compile time.

```java
Node<Integer> n1 = new Node<>(10);

n1.data = 20;       // OK
n1.data = "Hello";  // Compile-time error
```

A `Node<Integer>` cannot store a String.

This helps prevent type errors before the program runs.

Also, Java generics use reference types. Use `Integer`, not `int`, and `Double`, not `double`, as type arguments.

