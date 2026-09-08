
## Comparison Operators

| Operator | Description           | Example                   |
|----------|----------------------|---------------------------|
| `==`     | Equal to             | `5 == 5` → true          |
| `!=`     | Not equal to         | `5 != 3` → true          |
| `>`      | Greater than         | `5 > 3` → true           |
| `<`      | Less than            | `5 < 3` → false          |
| `>=`     | Greater than or equal| `5 >= 5` → true          |
| `<=`     | Less than or equal   | `5 <= 6` → true          |

**Compare numbers:**
```java
int a = 10, b = 20;
System.out.println(a < b); // true
```

**Compare Strings:**
```java
String s1 = "Hello";
String s2 = "World";
System.out.println(s1.equals(s2)); // false
```
## Logical Operators

- `&&` : AND  
- `||` : OR  
- `!`  : NOT  

**Example:**
```java
boolean a = true;
boolean b = false;

System.out.println(a && b); // false
System.out.println(a || b); // true
System.out.println(!a);     // false
```
### Short-Circuit Evaluation

Short-circuit evaluation means that in a logical expression, Java may **skip evaluating the second operand** if the result can already be determined from the first operand.


- `&&` (Logical AND)
- `||` (Logical OR)

## Rules

| Operator | Skip Right Operand When | Example |
|----------|------------------------|---------|
| `&&` | Left operand is false | `false && (anything)` → right not evaluated |
| `\|\|` | Left operand is true  | `true \|\| (anything)` → right not evaluated |


## Conditional Statements

### if
**if (condition) statement;** // or **blocks** `{...}` which is group of statements;
```java
int number = 2;
boolean isNumberEven;
if (number % 2 == 0) {
    isNumberEven = true; // Even number
} else {
    isNumberEven = false; // Odd number
}
```
### ternary operator 

**variable = (condition) ? valueIfconditionTrue : valueIfconditionFalse;**
```java
int number = 2;
boolean isNumberEven = (number % 2 == 0) ? true: false;
```



### switch
```java
int day = 2;

switch(day) {
    case 1:
        System.out.println("Monday");
        break;
    case 2:
        System.out.println("Tuesday");
        break;
    default:
        System.out.println("Other day");
}
// Output: Tuesday
```
 ## StringTokenizer
- `"Hello world Java"` — how can we separate each word?
- `StringTokenizer` breaks a string into smaller parts (tokens) using **delimiters** (default: space " ")
```java
import java.util.StringTokenizer;

String sentence = "Hello world Java";
StringTokenizer st1 = new StringTokenizer(sentence);// default delimiter " " space
System.out.println(st1.nextToken()); // Hello

String data = "apple,banana,orange";
StringTokenizer st2 = new StringTokenizer(data, ","); // using "," as separator
System.out.println(st2.nextToken()); // apple
```