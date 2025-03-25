# Object-Oriented Programming (OOP) Concepts in Dart  

## **🔹 What is OOP?**  
Object-Oriented Programming (OOP) is a programming paradigm that uses **objects** and **classes** to structure code.  

✅ **Key Benefits of OOP:**  
✔ Code Reusability  
✔ Modularity  
✔ Scalability  
✔ Data Security (Encapsulation)  

---
### **Class and Object in Dart**  
In **Dart**, everything revolves around **classes and objects** because Dart is an **object-oriented** programming language.  

---

## **1. What is a Class?**  
A **class** is a **blueprint** for creating objects. It defines the **properties (variables)** and **behaviors (methods)** an object will have.

### **Syntax of a Class in Dart**  
```dart
class ClassName {
  // Properties (variables)
  // Methods (functions)
}
```

---

## **2. What is an Object?**  
An **object** is an **instance** of a class. It has a **unique identity** and can **access class properties and methods**.

### **Syntax to Create an Object**  
```dart
ClassName objectName = ClassName();  // Creating an object
```

---

## **Example: Creating a Class and Object in Dart**
```dart
class Car {
  // Properties (variables)
  String brand;
  int speed;

  // Constructor
  Car(this.brand, this.speed);

  // Method (function)
  void displayInfo() {
    print("Car Brand: $brand");
    print("Top Speed: $speed km/h");
  }
}

void main() {
  // Creating an object of the Car class
  Car myCar = Car("Toyota", 180);

  // Accessing object properties and methods
  myCar.displayInfo();
}
```

### **Output:**
```
Car Brand: Toyota
Top Speed: 180 km/h
```

---

## **3. Understanding Objects in Detail**
Each **object** has:
- **State** → Defined by **properties** (e.g., `brand`, `speed`).
- **Behavior** → Defined by **methods** (e.g., `displayInfo()`).
- **Identity** → A unique reference in memory.

```dart
void main() {
  Car car1 = Car("BMW", 250);
  Car car2 = Car("Tesla", 220);

  car1.displayInfo();
  car2.displayInfo();
}
```
### **Output:**
```
Car Brand: BMW
Top Speed: 250 km/h
Car Brand: Tesla
Top Speed: 220 km/h
```
**Each object has its own data.**

---

## **4. Constructor in Dart**
A constructor is a **special method** that is called **automatically** when an object is created.

### **Parameterized Constructor**
```dart
class Person {
  String name;
  int age;

  // Constructor
  Person(this.name, this.age);

  void showDetails() {
    print("Name: $name, Age: $age");
  }
}

void main() {
  Person p1 = Person("Alice", 25);
  p1.showDetails(); // Output: Name: Alice, Age: 25
}
```
---

## **5. Default Constructor (Implicit)**
If you don’t define a constructor, Dart provides a **default constructor** with no arguments.

```dart
class Bike {
  String brand = "Honda";
  int speed = 150;
}

void main() {
  Bike myBike = Bike();
  print(myBike.brand); // Output: Honda
}
```

---

## **6. Default Constructor( Explicit)**  
You can explicitly define a **default constructor** without parameters.

### **Example: Default Constructor (Explicit)**  
```dart
class Car {
  String brand;
  int speed;

  // Default Constructor (Explicit)
  Car() {
    brand = "Honda";
    speed = 200;
  }

  void display() {
    print("Brand: $brand, Speed: $speed km/h");
  }
}

void main() {
  Car myCar = Car();
  myCar.display();
}
```
### **Output:**  
```
Brand: Honda, Speed: 200 km/h
```

---
## **7. Named Constructor**
Dart allows **multiple constructors** using named constructors.

```dart
class Laptop {
  String brand;
  int ram;

  // Default Constructor
  Laptop(this.brand, this.ram);

  // Named Constructor
  Laptop.highPerformance() {
    brand = "Alienware";
    ram = 32;
  }

  void showSpecs() {
    print("Brand: $brand, RAM: ${ram}GB");
  }
}

void main() {
  Laptop gamingLaptop = Laptop.highPerformance();
  gamingLaptop.showSpecs();  // Output: Brand: Alienware, RAM: 32GB
}
```

---

## **8. Private Properties with Getter and Setter**
Dart allows **encapsulation** using **private properties (`_property`)** with **getter and setter**.

```dart
class BankAccount {
  String accountHolder;
  double _balance; // Private variable

  BankAccount(this.accountHolder, this._balance);

  // Getter
  double get balance => _balance;

  // Setter
  set deposit(double amount) {
    if (amount > 0) {
      _balance += amount;
      print("Deposited: \$${amount}");
    } else {
      print("Invalid deposit amount!");
    }
  }
}

void main() {
  var account = BankAccount("John Doe", 1000);
  print("Balance: \$${account.balance}"); // Accessing balance via getter

  account.deposit = 500; // Using setter
  print("New Balance: \$${account.balance}");
}
```

---

# **9.Static Variables and Methods in Dart**  

In **Dart**, `static` variables and methods belong to the **class itself** rather than to individual objects. They are shared among all instances of the class. 

✅ A **static method** can be called **without creating an object**.  
✅ It **cannot access non-static (instance) variables**.  
✅ Used for **utility functions** that don’t depend on instance variables.  



```dart
class MathOperations {
  static double pi = 3.14;

  static double square(double num) {
    return num * num;
  }
}

void main() {
  print(MathOperations.pi); // Accessing static variable
  print(MathOperations.square(4)); // Calling static method
}
```

---


---

# **🔹 Four Pillars of OOP in Dart**  

| **Concept** | **Definition** | **Keywords Used** |
|------------|--------------|----------------|
| **Encapsulation** | Wrapping data (variables) and code (methods) together in a single unit (class) | `private variables (_var)`, `getters`, `setters` |
| **Inheritance** | One class acquires the properties and behaviors of another class | `extends`, `super` |
| **Polymorphism** | A method behaves differently in different contexts | `@override`, `operator` |
| **Abstraction** | Hiding implementation details and exposing only necessary functionalities | `abstract`, `implements` |

---

# Encapsulation in Dart 
Encapsulation is one of the fundamental **OOP principles** that helps in **data hiding** and ensures that data is not directly modified from outside the class.

---

## **🔹 Key Features of Encapsulation in Dart**
✅ Use **private variables** (`_variableName`) to restrict direct access.  
✅ Provide **getters** to access data.  
✅ Provide **setters** to update data with validation.  
✅ Ensure **data integrity and security**.  

---

## 1.Encapsulation Using Getters and Setters
We **restrict direct access** to variables using **private variables** and allow controlled access via **getters and setters**.

```dart
class Student {
  String _name;  // Private variable
  int _age;      // Private variable

  // Constructor
  Student(this._name, this._age);

  // Getter for name
  String get name => _name;

  // Setter for name with validation
  set name(String newName) {
    if (newName.isNotEmpty) {
      _name = newName;
    } else {
      print("❌ Error: Name cannot be empty!");
    }
  }

  // Getter for age
  int get age => _age;

  // Setter for age with validation
  set age(int newAge) {
    if (newAge > 0) {
      _age = newAge;
    } else {
      print("❌ Error: Age must be a positive number!");
    }
  }

  void display() {
    print("Student: $_name, Age: $_age");
  }
}

void main() {
  Student s1 = Student("Alice", 20);
  s1.display();

  s1.age = -5;  // ❌ Invalid age (Validation will prevent update)
  s1.age = 25;  // ✅ Valid update
  s1.display();
}
```

### **Output**
```
Student: Alice, Age: 20
❌ Error: Age must be a positive number!
Student: Alice, Age: 25
```
📌 **Benefits:**  
- **Encapsulation prevents invalid data entry.**  
- **Encapsulation provides controlled access to data.**  

---

## 2.Read-Only Data (Getter Only, No Setter)
If we want to make a variable **read-only**, we provide only a **getter** and **no setter**.

```dart
class BankAccount {
  String _accountHolder;
  double _balance;

  BankAccount(this._accountHolder, this._balance);

  // Getter (Read-Only)
  double get balance => _balance;

  void showDetails() {
    print("Account Holder: $_accountHolder");
    print("Balance: $_balance");
  }
}

void main() {
  BankAccount account = BankAccount("John", 5000);
  print("Balance: ${account.balance}"); // ✅ Allowed
  // account.balance = 10000; // ❌ Error: No setter available
}
```
### **Output**
```
Balance: 5000.0
```
📌 **Key Benefit:** Users can **view** the balance but **cannot modify it directly**.

---

## 3.Encapsulation with Constructor Validation
We can enforce **validation at object creation** using constructors.

```dart
class Employee {
  String _name;
  double _salary;

  // Constructor with validation
  Employee(this._name, this._salary) {
    if (_salary < 0) {
      print("❌ Salary cannot be negative! Setting default salary.");
      _salary = 0;
    }
  }

  void display() {
    print("Employee: $_name, Salary: $_salary");
  }
}

void main() {
  Employee emp1 = Employee("Robert", -5000); // Invalid salary
  emp1.display();
}
```
### **Output**
```
❌ Salary cannot be negative! Setting default salary.
Employee: Robert, Salary: 0.0
```
📌 **Benefit:** Prevents invalid data **at object creation**.

---
# Inheritance in Dart   

## **🔹 What is Inheritance?**
Inheritance is an **Object-Oriented Programming (OOP)** feature that allows a **child class** to acquire properties and behaviors (methods) from a **parent class**.  

✅ **Benefits:**  
✔ Code Reusability  
✔ Avoids Duplication  
✔ Establishes Hierarchical Relationships  

📌 **Dart supports single inheritance but provides alternatives for multiple inheritance using Mixins and Interfaces.**  

---

## **🔹 Types of Inheritance in Dart**
| **Type** | **Supported in Dart?** | **Keyword Used** |
|---------|----------------|--------------|
| **Single Inheritance** | ✅ Yes | `extends` |
| **Multi-Level Inheritance** | ✅ Yes | `extends` |
| **Hierarchical Inheritance** | ✅ Yes | `extends` |
| **Multiple Inheritance** | ❌ No | Use **Mixins (`with`)** or **Interfaces (`implements`)** |
| **Hybrid Inheritance** | ❌ No | Achievable via Mixins & Interfaces |

---

## **1️⃣ Single Inheritance (Supported ✅)**
A **child class** inherits from only **one parent class** using the `extends` keyword.  

### **Example:**
```dart
class Animal {
  void eat() {
    print("Animal is eating");
  }
}

class Dog extends Animal {
  void bark() {
    print("Dog is barking");
  }
}

void main() {
  Dog d = Dog();
  d.eat();  // Inherited from Animal
  d.bark();
}
```
### **Output:**
```
Animal is eating
Dog is barking
```
📌 **Dart supports single inheritance using `extends`.**  

---

## **2️⃣ Multi-Level Inheritance (Supported ✅)**
A class inherits from another child class, forming a **chain of inheritance**.  

### **Example:**
```dart
class Animal {
  void eat() {
    print("Animal is eating");
  }
}

class Mammal extends Animal {
  void breathe() {
    print("Mammal is breathing");
  }
}

class Dog extends Mammal {
  void bark() {
    print("Dog is barking");
  }
}

void main() {
  Dog d = Dog();
  d.eat();     // From Animal
  d.breathe(); // From Mammal
  d.bark();    // From Dog
}
```
### **Output:**
```
Animal is eating
Mammal is breathing
Dog is barking
```
📌 **Dart allows multi-level inheritance, enabling deeper hierarchies.**  

---

## **3️⃣ Hierarchical Inheritance (Supported ✅)**
Multiple child classes inherit from the **same parent class**.  

### **Example:**
```dart
class Animal {
  void eat() {
    print("Animal is eating");
  }
}

class Dog extends Animal {
  void bark() {
    print("Dog is barking");
  }
}

class Cat extends Animal {
  void meow() {
    print("Cat is meowing");
  }
}

void main() {
  Dog d = Dog();
  d.eat();
  d.bark();

  Cat c = Cat();
  c.eat();
  c.meow();
}
```
### **Output:**
```
Animal is eating
Dog is barking
Animal is eating
Cat is meowing
```
📌 **Multiple child classes can inherit from a common parent class.**  

---

## **4️⃣ Multiple Inheritance (Not Supported ❌)**
Dart **does not support multiple inheritance** directly (one class cannot extend multiple classes).  

🔴 **Example (Not Allowed in Dart)**
```dart
class A {}
class B {}
class C extends A, B {} // ❌ ERROR: Dart does not support multiple inheritance
```
📌 **Solution:** Use **Mixins or Interfaces** instead.  

---

## **5️⃣ Multiple Inheritance Using Mixins (Alternative ✅)**
Since Dart **does not support multiple inheritance**, we use **mixins (`with` keyword)** to inherit from multiple sources.  

### **Example:**
```dart
mixin Flyable {
  void fly() {
    print("Can fly");
  }
}

mixin Swimmable {
  void swim() {
    print("Can swim");
  }
}

class Bird with Flyable, Swimmable {
  void display() {
    print("I am a bird");
  }
}

void main() {
  Bird b = Bird();
  b.display();
  b.fly();
  b.swim();
}
```
### **Output:**
```
I am a bird
Can fly
Can swim
```
📌 **Mixins allow a class to inherit behavior from multiple sources, simulating multiple inheritance.**  

---

## **6️⃣ Multiple Inheritance Using Interfaces (Alternative ✅)**
Dart allows multiple inheritance-like behavior using **interfaces** (`implements` keyword).  

### **Example:**
```dart
class A {
  void showA() {
    print("Class A method");
  }
}

class B {
  void showB() {
    print("Class B method");
  }
}

// Class C implements A and B
class C implements A, B {
  @override
  void showA() {
    print("Implemented showA in Class C");
  }

  @override
  void showB() {
    print("Implemented showB in Class C");
  }
}

void main() {
  C obj = C();
  obj.showA();
  obj.showB();
}
```
### **Output:**
```
Implemented showA in Class C
Implemented showB in Class C
```
📌 **Interfaces allow us to implement multiple classes, simulating multiple inheritance.**  

---

## **7️⃣ Hybrid Inheritance (Not Supported ❌)**
Hybrid inheritance (a mix of multiple inheritance and other types) **is not directly supported in Dart**, but can be achieved using **mixins and interfaces**.  

---
# Polymorphism in Dart   

## **🔹 What is Polymorphism?**  
Polymorphism is an **OOP concept** where a single function, class, or operator behaves **differently** based on the context. In Dart, polymorphism allows:  
✅ **Method Overriding** (Runtime Polymorphism)  
✅ **Method Overloading** (Not directly supported)  
✅ **Operator Overloading**  

---

## **1️⃣ Method Overriding (Runtime Polymorphism ✅)**  
When a **child class** provides a **new implementation** for a method already defined in the **parent class**.  

### **Example:**  
```dart
class Animal {
  void makeSound() {
    print("Animal makes a sound");
  }
}

class Dog extends Animal {
  @override
  void makeSound() {
    print("Dog barks");
  }
}

class Cat extends Animal {
  @override
  void makeSound() {
    print("Cat meows");
  }
}

void main() {
  Animal a; 

  a = Dog();
  a.makeSound(); // Calls Dog's method

  a = Cat();
  a.makeSound(); // Calls Cat's method
}
```
### **Output:**
```
Dog barks
Cat meows
```
📌 **The overridden method in the child class is executed instead of the parent class method.**  

---

## **2️⃣ Method Overloading (Not Directly Supported ❌)**  
Dart does **not support method overloading** (multiple methods with the same name but different parameters). Instead, you can achieve similar behavior using:  
✔ **Optional Parameters**  
✔ **Named Parameters**  

### **Example using Optional Parameters:**
```dart
class MathOperations {
  void add(int a, [int? b]) {
    if (b != null) {
      print("Sum: ${a + b}");
    } else {
      print("Single number: $a");
    }
  }
}

void main() {
  MathOperations obj = MathOperations();
  obj.add(5, 10); // With two parameters
  obj.add(7);     // With one parameter
}
```
### **Output:**
```
Sum: 15
Single number: 7
```
📌 **Dart does not allow function overloading but supports optional and named parameters to achieve similar behavior.**  

---

## **3️⃣ Operator Overloading (Supported ✅)**
Dart allows **overloading operators** by defining the behavior of an operator (`+`, `-`, `*`, etc.) for a custom class.  

### **Example:**  
```dart
class Point {
  int x, y;

  Point(this.x, this.y);

  // Overloading the + operator
  Point operator +(Point other) {
    return Point(x + other.x, y + other.y);
  }

  void display() {
    print("Point($x, $y)");
  }
}

void main() {
  Point p1 = Point(3, 4);
  Point p2 = Point(1, 2);

  Point p3 = p1 + p2; // Using overloaded + operator
  p3.display();
}
```
### **Output:**
```
Point(4, 6)
```
📌 **We have redefined the `+` operator for the `Point` class, enabling custom addition behavior.**  

---
# Abstraction in Dart  

## **🔹 What is Abstraction?**  
Abstraction is an **OOP concept** that hides **implementation details** and only exposes the **essential functionalities**.  

✅ **Benefits of Abstraction:**  
✔ Hides unnecessary details from the user  
✔ Improves code maintainability  
✔ Supports loose coupling  

📌 **In Dart, abstraction is achieved using:**  
1️⃣ **Abstract Classes**  
2️⃣ **Interfaces**  

---

## **1️⃣ Abstract Classes in Dart**  
An **abstract class** is a class that **cannot be instantiated** and can have **abstract (unimplemented) methods**.  

### **Example:**
```dart
// Abstract class
abstract class Animal {
  void makeSound(); // Abstract method (no implementation)

  void sleep() { // Concrete method (has implementation)
    print("Sleeping...");
  }
}

// Subclass implementing the abstract method
class Dog extends Animal {
  @override
  void makeSound() {
    print("Dog barks");
  }
}

void main() {
  Dog d = Dog();
  d.makeSound(); // Calls overridden method
  d.sleep();     // Calls parent class method
}
```
### **Output:**
```
Dog barks
Sleeping...
```
📌 **An abstract class can have both abstract (unimplemented) and concrete (implemented) methods.**  

---

## **2️⃣ Abstraction Using Interfaces**  
Dart does not have a separate keyword for **interfaces**. Instead, **any class can act as an interface** using the `implements` keyword.  

### **Example:**  
```dart
// Interface
class Vehicle {
  void start(); // Abstract method
}

// Class implementing the interface
class Car implements Vehicle {
  @override
  void start() {
    print("Car started");
  }
}

void main() {
  Car c = Car();
  c.start();
}
```
### **Output:**
```
Car started
```
📌 **In Dart, interfaces must implement all the methods defined in the interface class.**  

---

## **🔹 Key Differences: Abstract Class vs Interface**
| Feature | Abstract Class | Interface |
|---------|---------------|-----------|
| **Can have concrete methods?** | ✅ Yes | ❌ No (only method declarations) |
| **Can have constructors?** | ✅ Yes | ❌ No |
| **Can have instance variables?** | ✅ Yes | ❌ No |
| **Supports multiple inheritance?** | ❌ No (Single Inheritance) | ✅ Yes (Multiple Interfaces using `implements`) |

---
# Mixin and Interfaces in Dart   

Dart does **not support multiple inheritance**, but it provides **mixins and interfaces** to enable **code reuse** and **multiple behaviors** in classes.

---

## **🔹 Mixins in Dart**  
A **mixin** is a way to **reuse methods** from one class in another **without inheritance**.  
✔ Used when a class needs additional functionalities but **doesn’t need to extend another class**.  
✔ Declared using the `mixin` keyword.  
✔ Used with the `with` keyword.

---

### **✅ Example: Using Mixins**
```dart
mixin CanFly {
  void fly() {
    print("Flying...");
  }
}

mixin CanSwim {
  void swim() {
    print("Swimming...");
  }
}

class Bird with CanFly {} // Adding flying ability

class Fish with CanSwim {} // Adding swimming ability

class Duck with CanFly, CanSwim {} // Duck can both fly and swim

void main() {
  Duck d = Duck();
  d.fly();  // Output: Flying...
  d.swim(); // Output: Swimming...
}
```
📌 **Mixins allow multiple inheritance-like behavior without extending multiple classes.**

---

## Interfaces in Dart  
Dart **does not have a separate keyword for interfaces** like Java or C++. Instead, **any class can act as an interface** using the `implements` keyword.  
✔ **All methods of the interface must be implemented in the subclass.**  
✔ Unlike mixins, **interfaces do not provide default implementations**.  

---

### **✅ Example: Using Interfaces**
```dart
class Vehicle {
  void start(); // Abstract method
}

class Car implements Vehicle {
  @override
  void start() {
    print("Car started");
  }
}

void main() {
  Car myCar = Car();
  myCar.start(); // Output: Car started
}
```
📌 **Since Dart doesn’t support multiple inheritance, interfaces allow classes to inherit behaviors without inheriting implementation.**  

---










