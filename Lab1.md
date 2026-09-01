
## First Java Program Basics

1. Must have a **class**  
2. **Class name should use PascalCase** (start with a capital letter)  
3. **Filename must match the public class name**  
4. Program execution **starts from `main` method:**
    ```java
    public static void main(String[] args)
    ```
5. **Compile first, then run:**
    ```bash
    javac FileName.java
    java FileName
    ```

### Minimal Example

Filename: HelloWorld.java
```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}
```
### Error & Debugging
| **Error Type**    | **Description**                                                             | **Example**                              |
| ----------------- | --------------------------------------------------------------------------- | ---------------------------------------- |
| **Syntax Error**  | Grammatical mistake in the program. The program will not compile.           | `int x = 10` *(missing semicolon)*       |
| **Runtime Error** | Program compiles successfully, but when it runs, it shows an error message. | `int a = 10 / 0;` *(division by zero)*   |
| **Logic Error**   | Program compiles and runs without any error, but the output is incorrect.   | `int sum = a - b;` *(should be `a + b`)* |


