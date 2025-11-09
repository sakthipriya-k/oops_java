💻 Object-Oriented Programming (OOPS) – Java Notes with Examples

📘 Covered Concepts:

**1️⃣ Class & Object**
**2️⃣ Constructor (Default, Parameterized, Overloaded)**
**3️⃣ this Keyword**
**4️⃣ Static Members & Methods**
**5️⃣ Inheritance (Single, Multilevel, Hierarchical, Hybrid)**
**6️⃣ super Keyword & Constructor Chaining**
**7️⃣ Encapsulation**
**8️⃣ Abstraction (Abstract Class & Interface)**
**9️⃣ Polymorphism (Compile-time & Run-time)**

---

## 🧩 1. Class & Object

**Class** – Blueprint/template for creating objects.
**Object** – Instance of a class.

✅ Example (Using `this`, constructor, parameters, methods):

```java
class Student {
    String name;
    int rn;

    Student(String name, int rn) {
        this.name = name;
        this.rn = rn;
    }

    void displayInfo() {
        System.out.println("name : " + name);
        System.out.println("rollnumber : " + rn);
    }
}

public class Demo {
    public static void main(String[] args) {
        Student s1 = new Student("priya", 18);
        Student s2 = new Student("sakthi", 19);

        s1.displayInfo();
        System.out.println();
        s2.displayInfo();
    }
}
```

---

## 🏗️ 2. Constructor

### ➤ What is a Constructor?

* A **special method** to initialize objects.
* Called **automatically** when an object is created.
* Same name as class.
* No return type.

### 🔸 Types:

1. **Default Constructor**
2. **Parameterized Constructor**
3. **Constructor Overloading**

✅ Example (Overloading):

```java
class Demo {
    int x, y;
    Demo() { x=0; y=0; }
    Demo(int a) { x=a; y=0; }
    Demo(int a, int b) { x=a; y=b; }

    void display() {
        System.out.println("x = " + x + ", y = " + y);
    }
}
```

---

## 🧭 3. Static Keyword

* Belongs to the **class**, not objects.
* Accessed without creating an object.

✅ Example:

```java
class Account {
    static int accountCount = 0;
    String holder;
    int balance;

    Account(String h, int b) {
        holder = h;
        balance = b;
        accountCount++;
    }

    void display() {
        System.out.println("Account Holder: " + holder + ", Balance: " + balance);
    }

    static void showTotal() {
        System.out.println("Total accounts: " + accountCount);
    }
}
```

---

## 🧬 4. Inheritance

**Definition:** Acquiring properties & behaviors of one class by another.
**Keyword:** `extends`

### 🔸 Types of Inheritance:

* Single
* Multilevel
* Hierarchical
* Hybrid

✅ Example (Multilevel):

```java
class Person {
    Person(){ System.out.println("person is created"); }
}
class Employee extends Person {
    Employee(){ System.out.println("employee is created"); }
}
class Manager extends Employee {
    Manager(){ System.out.println("manager is created"); }
}
```

Output:

```
person is created
employee is created
manager is created
```

---

## ⚙️ 5. this and super

* `this` → Refers to **current class** variables or methods.
* `super` → Refers to **parent class** variables, methods, or constructor.

✅ Example:

```java
class Vehicle {
    int speed;
    Vehicle(int speed) {
        this.speed = speed;
        System.out.println("Vehicle speed set is " + this.speed);
    }
}

class Car extends Vehicle {
    String model;
    Car(int speed, String model) {
        super(speed);
        this.model = model;
        System.out.println("Car model is " + model);
    }
}
```

---

## 🔒 6. Encapsulation

**Definition:** Wrapping data (variables) and methods into a single unit and restricting direct access using `private`.

✅ Example:

```java
class Product {
    private int price;

    public void setPrice(int p) {
        if (p > 1000) price = p;
        else System.out.println("Invalid price!!");
    }

    public int getPrice() {
        return price;
    }
}
```

---

## 🧠 7. Abstraction

**Definition:** Hiding internal details and showing only essential features.

### ➤ Using Abstract Class:

```java
abstract class Employee {
    abstract void calculateSalary();
    void companyName() {
        System.out.println("Works at ABC Corp");
    }
}

class Manager extends Employee {
    void calculateSalary() {
        System.out.println("Manager salary is 50000");
    }
}
```

### ➤ Using Interface:

```java
interface Vehicle {
    void move();
}

class Bike implements Vehicle {
    public void move() {
        System.out.println("bike moves fast");
    }
}
```

---

## 🔄 8. Polymorphism

**Definition:** One thing, many forms.

### ➤ Compile-time (Method Overloading)

```java
class Calculator {
    int multiply(int a, int b) { return a * b; }
    int multiply(int a, int b, int c) { return a * b * c; }
}
```

### ➤ Run-time (Method Overriding)

```java
class Animal {
    void sound() { System.out.println("Animal makes sound"); }
}
class Cat extends Animal {
    void sound() { System.out.println("Cats meow"); }
}
```

---

## 🧾 Summary – OOPS Concepts Recap

| Concept        | Keyword                  | Description                     |
| -------------- | ------------------------ | ------------------------------- |
| Class & Object | `class`                  | Blueprint and instance          |
| Constructor    | —                        | Initializes object              |
| this           | `this`                   | Refers to current class object  |
| Static         | `static`                 | Shared among all objects        |
| Inheritance    | `extends`                | Reuse parent class code         |
| super          | `super`                  | Calls parent constructor/method |
| Encapsulation  | `private`, `get/set`     | Data protection                 |
| Abstraction    | `abstract`, `interface`  | Hides internal details          |
| Polymorphism   | Overloading / Overriding | One name, many forms            |

---
