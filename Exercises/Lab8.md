# Lab 8: Inheritance and Polymorphism Problem-Solving

## General Instructions

1. Complete the required `.java` files.
2. Do not change the provided `main()` methods.
3. Use `private` for fields.
4. Use `public` for required constructors and methods.
5. Use `extends`, `super()`, and `@Override` where specified.
6. Do not use `protected`.

---

## Exercise 1: Vehicle Rental System

**Concepts:** Inheritance, constructors, `super()`, getters, arrays, searching

### Given: `RentalTest.java`

```java
public class RentalTest {
    public static void main(String[] args) {
        RentalCar[] cars = {
            new RentalCar("Toyota", 50, 7),
            new RentalCar("Honda", 65, 5),
            new RentalCar("Ford", 45, 10)
        };

        RentalCar result = findMostExpensive(cars);

        System.out.println("Car: " + result.getModel());
        System.out.println("Daily Rate: " + result.getDailyRate());
        System.out.println("Rental Days: " + result.getRentalDays());
        System.out.println("Total Cost: " + result.getTotalCost());
    }

    public static RentalCar findMostExpensive(RentalCar[] cars) {
        // TODO: Return the car with the highest total rental cost.
        return null;
    }
}
```

### Your tasks

**1. `Vehicle.java`**

- Private fields: `model` (`String`) and `dailyRate` (`double`).
- Public constructor: `Vehicle(String model, double dailyRate)`.
- Public getters: `getModel()` and `getDailyRate()`.

**2. `RentalCar.java`**

- Extend `Vehicle`.
- Private field: `rentalDays` (`int`).
- Public constructor: `RentalCar(String model, double dailyRate, int rentalDays)`.
- Use `super(model, dailyRate)`.
- Public getter: `getRentalDays()`.
- Public method `getTotalCost()` returns the daily rate multiplied by the rental days.

**3. Complete `findMostExpensive()`**

Return the car with the highest total rental cost.

### Expected output

```text
Car: Ford
Daily Rate: 45.0
Rental Days: 10
Total Cost: 450.0
```

---

## Exercise 2: Notification System

**Concepts:** Method overriding, runtime polymorphism, dynamic method dispatch

### Given: `NotificationTest.java`

```java
public class NotificationTest {
    public static void main(String[] args) {
        Notification[] messages = {
            new EmailNotification(),
            new TextNotification(),
            new EmailNotification()
        };

        for (Notification message : messages) {
            message.send();
        }
    }
}
```

### Your tasks

**1. `Notification.java`**

- Public method `send()` prints `"Sending a general notification"`.

**2. `EmailNotification.java`**

- Extend `Notification`.
- Override `send()` to print `"Sending an email"`.

**3. `TextNotification.java`**

- Extend `Notification`.
- Override `send()` to print `"Sending a text message"`.

### Expected output

```text
Sending an email
Sending a text message
Sending an email
```

**Requirement:** Do not use `if` statements to determine which `send()` method runs. Java should select the overridden method at runtime.

---

## Exercise 3: Game Character

**Concepts:** Upcasting, downcasting, `instanceof`

### Given: `GameTest.java`

```java
public class GameTest {
    public static void main(String[] args) {
        Character player = new Wizard("Merlin", 80);

        System.out.println(player.getName());

        if (player instanceof Wizard) {
            Wizard wizard = (Wizard) player;
            wizard.castSpell();
        }

        Character anotherPlayer = new Character("Alex");

        if (anotherPlayer instanceof Wizard) {
            Wizard wizard = (Wizard) anotherPlayer;
            wizard.castSpell();
        }
    }
}
```

### Your tasks

**1. `Character.java`**

- Private field: `name`.
- Public constructor: `Character(String name)`.
- Public getter: `getName()`.

**2. `Wizard.java`**

- Extend `Character`.
- Private field: `mana` (`int`).
- Public constructor: `Wizard(String name, int mana)`.
- Use `super(name)`.
- Public method `castSpell()` prints `"Casting spell with "` followed by the mana value and `" mana"`.

### Expected output

```text
Merlin
Casting spell with 80 mana
```

### Questions

1. Which statement performs upcasting?
2. Which statement performs downcasting?
3. Why does the second `if` statement not execute?
4. What could happen if you tried to cast `anotherPlayer` to `Wizard` without checking its actual type?

---

## Exercise 4: Smart Home Devices

**Concepts:** Field hiding, method overriding, reference type, actual object type

### Given: `DeviceTest.java`

```java
class Device {
    String status = "Device is on standby";

    public String getStatus() {
        return status;
    }
}

class SmartLight extends Device {
    String status = "Smart light is on";

    @Override
    public String getStatus() {
        return status;
    }
}

public class DeviceTest {
    public static void main(String[] args) {
        Device d = new SmartLight();

        System.out.println(d.status);
        System.out.println(d.getStatus());
    }
}
```

### Your tasks

1. Do not change the code.
2. Write the output.
3. Explain why `d.status` and `d.getStatus()` produce different results.
4. Identify which access is determined at compile time and which method call is determined at runtime.

### Expected output

```text
Device is on standby
Smart light is on
```

---

## Exercise 5: Museum Ticket System

**Concepts:** Inheritance, constructor chaining, `super()`, private fields, method overriding

### Given: `TicketTest.java`

```java
public class TicketTest {
    public static void main(String[] args) {
        GuidedTicket ticket = new GuidedTicket(
            "Ancient History",
            25.0,
            "English"
        );

        ticket.displayInfo();
    }
}
```

### Your tasks

**1. `MuseumTicket.java`**

- Private fields: `exhibitionName` (`String`) and `price` (`double`).
- Public constructor: `MuseumTicket(String exhibitionName, double price)`.
- Public getters for both fields.
- Public method `displayInfo()` prints the exhibition name and ticket price.

**2. `GuidedTicket.java`**

- Extend `MuseumTicket`.
- Private field: `language` (`String`).
- Public constructor: `GuidedTicket(String exhibitionName, double price, String language)`.
- Use `super(exhibitionName, price)` to initialize the parent fields.
- Public getter: `getLanguage()`.
- Override `displayInfo()` to print the exhibition name, price, and tour language.

### Expected output

```text
Exhibition: Ancient History
Price: 25.0
Tour Language: English
```

---

## Submission Requirements

1. Submit all required `.java` files.
2. Do not change the provided `main()` methods.
3. Use private fields and public getters as specified.
4. Use inheritance and constructor chaining where required.
5. Verify that each program produces the expected output.

