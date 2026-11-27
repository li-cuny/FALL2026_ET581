# Java File Handling
---

## 1. File Management (File system operations)
Use **`File` class**:
- `exists()`
- `createNewFile()`
- `delete()`
- `length()`
- `getName()`
- `getAbsolutePath()`
- `list()`

**Important:**
The `File` class does **not** read or write file contents.

---

## 2. Character/Text Files (Human-readable)
Use for `.txt`, `.csv`, `.json`.

**Classes:**
- `FileWriter`
- `BufferedWriter`
- `FileReader`
- `BufferedReader`
- `Scanner`

---

## 3. Binary Files (Images, audio, video)
Use for non-text data like `.png`, `.mp3`, `.mp4`.

**Classes:**
- `FileInputStream`
- `FileOutputStream`
- `BufferedInputStream`
- `BufferedOutputStream`

---

## 4. Java File Read and Write

### 4.1 Introduction
Java provides multiple APIs to read and write files. The most common and modern approach is using the `java.nio.file` package, but older approaches like `FileReader`, `BufferedReader`, and `FileWriter` are still widely used.

---

### 4.2 Reading Files

#### 4.2.1 Using Files.readAllLines()
```java
import java.nio.file.*;
import java.io.*;
import java.util.*;

public class ReadExample {
    public static void main(String[] args) throws Exception {
        List<String> lines = Files.readAllLines(Path.of("data.txt"));
        for (String line : lines) {
            System.out.println(line);
        }
    }
}
```

#### 4.2.2 Using Files.lines(inputPath)
```java
import java.nio.file.Files;
import java.nio.file.Path;
import java.io.IOException;
import java.util.List;
import java.util.stream.Collectors;
import java.util.stream.Stream;

public class StreamFileExample {
    public static void main(String[] args) {
        Path inputPath = Path.of("input.txt");
        Path outputPath = Path.of("output.txt");

        try (Stream<String> lines = Files.lines(inputPath)) {
            List<String> upperLines = lines
                    .map(String::toUpperCase)
                    .collect(Collectors.toList());

            Files.write(outputPath, upperLines);
            System.out.println("Processing complete. Check output.txt");

        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

#### 4.2.3 Using BufferedReader (Traditional & Efficient)
```java
import java.io.*;

public class BufferedReaderExample {
    public static void main(String[] args) throws Exception {
        BufferedReader br = new BufferedReader(new FileReader("data.txt"));
        String line;
        while ((line = br.readLine()) != null) {
            System.out.println(line);
        }
        br.close();
    }
}
```
* try-with-resource
```java
try (BufferedReader br = new BufferedReader(new FileReader("data.txt"))) {

    String line;
    while ((line = br.readLine()) != null) {
        System.out.println(line);
    }
    //try-with-rerouse will call br.close()
    // br.close() will call fileReader.close()
} catch (Exception e) {
    e.printStackTrace();
}
```
---

### 4.3 Writing Files

#### 4.3.1 Using Files.writeString()
```java
import java.nio.file.*;

public class WriteExample {
    public static void main(String[] args) throws Exception {
        Files.writeString(Path.of("output.txt"), "Hello World!");
    }
}
```

#### 4.3.2 Using BufferedWriter
```java
import java.io.*;

public class BufferedWriterExample {
    public static void main(String[] args) throws Exception {
        BufferedWriter bw = new BufferedWriter(new FileWriter("output.txt"));
        bw.write("Hello World!");
        bw.newLine();
        bw.write("Second line");
        bw.close();
    }
}
```

---

### 4.4 Reading CSV Files 
```java
import java.io.*;

public class CSVExample {
    public static void main(String[] args) {
        try (BufferedReader br = new BufferedReader(new FileReader("data.csv"))) {
            String line;

            while ((line = br.readLine()) != null) {
                String[] parts = line.split(",");

                String name = parts[0];
                int age = Integer.parseInt(parts[1]);      // parse int
                double salary = Double.parseDouble(parts[2]); // parse double

                System.out.println("Name: " + name +
                                   ", Age: " + age +
                                   ", Salary: " + salary);
            }

        } catch (IOException e) {
            System.out.println("File error");
        } catch (NumberFormatException e) {
            System.out.println("Invalid number format in file");
        } catch (ArrayIndexOutOfBoundsException e) {
            System.out.println("Missing data in line");
        }
    }
```

---

### 4.5 Writing CSV Files
```java
import java.io.*;

public class WriteCSV {
    public static void main(String[] args) throws Exception {
        BufferedWriter bw = new BufferedWriter(new FileWriter("data.csv"));
        bw.write("John,25");
        bw.newLine();
        bw.write("Mary,30");
        bw.close();
    }
}
```

---

### 4.6 Best Practices
- Always close readers/writers (or use try-with-resources)
- Prefer `java.nio.file` for modern applications
- Use `BufferedReader`/`BufferedWriter` for large files
- Validate CSV fields before parsing

---

## 5. Text (Character) I/O

| Reader (Input)                  | Writer (Output)                   | Notes / Use Case                                                                        |
| ------------------------------- | --------------------------------- | --------------------------------------------------------------------------------------- |
| `FileReader`                    | `FileWriter`                      | Low-level character reading/writing. Usually wrapped in buffered versions.              |
| `BufferedReader`                | `BufferedWriter`                  | Most common pattern. Efficient line-by-line text I/O.                                   |
| `Scanner`                       | `PrintWriter`                     | Reads tokens/lines; prints formatted text. Good for parsing and formatted output.       |
| `Files.newBufferedReader(Path)` | `Files.newBufferedWriter(Path)`   | Modern, buffered, supports charset. Preferred for new code.                             |
| `Files.readAllLines(Path)`      | `Files.writeString(Path, String)` | Convenience methods for small files. Reads all lines into memory / writes whole string. |
| `Files.lines(Path)`             | `Files.write(Path, List<String>)` | Stream-based modern API. Lazy reading / writing multiple lines.                         |

## 6. Binary (Byte) I/O

| InputStream (Input)          | OutputStream (Output)         | Notes / Use Case                                                                        |
| ---------------------------- | ----------------------------- | --------------------------------------------------------------------------------------- |
| `FileInputStream`            | `FileOutputStream`            | Low-level byte streams. Direct read/write of binary files.                              |
| `BufferedInputStream`        | `BufferedOutputStream`        | Wrap low-level streams for efficiency. Common for large files or frequent reads/writes. |
| `Files.newInputStream(Path)` | `Files.newOutputStream(Path)` | Modern, low-level streams. Can wrap in buffered streams for efficiency.                 |
| N/A                          | `Files.write(Path, byte[])`   | Modern convenience method to write byte arrays.                                         |