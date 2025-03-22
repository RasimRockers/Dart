### Functions in Dart 

Functions are a fundamental part of Dart programming, allowing you to encapsulate code into reusable blocks. In Dart, functions help in modularity, readability, and maintainability of the code.

---

## **1. Defining a Function**
A function in Dart is defined using the `returnType functionName(parameters) { body }` syntax.

### **Example:**
```dart
void greet() {
  print("Hello, Dart!");
}
```
Here:
- `void` → Return type (no value is returned)
- `greet` → Function name
- `{ print("Hello, Dart!"); }` → Function body

---

## **2. Calling a Function**
To execute a function, simply call its name followed by parentheses.

```dart
void main() {
  greet(); // Function call
}
```

---

## **3. Function with Parameters**
Parameters allow passing values to a function.

### **Example:**
```dart
void greetUser(String name) {
  print("Hello, $name!");
}

void main() {
  greetUser("John");
}
```

---

## **4. Function with Return Value**
A function can return a value using the `return` statement.

### **Example:**
```dart
int add(int a, int b) {
  return a + b;
}

void main() {
  int sum = add(5, 3);
  print("Sum: $sum");
}
```
Here:
- The function `add(int a, int b)` takes two integers as parameters.
- It returns their sum.

---

## **5. Optional Parameters**
Dart supports optional parameters in three ways:
### **a) Positional Optional Parameters** (Use square brackets `[]`)
```dart
void greet([String name = "Guest"]) {
  print("Hello, $name!");
}

void main() {
  greet();       // Output: Hello, Guest!
  greet("Alice"); // Output: Hello, Alice!
}
```
```dart
void printSum(int a, [int b = 5]) {
  print("Sum: ${a + b}");
}

void main() {
  printSum(10, 20); // Output: Sum: 30
  printSum(10);     // Output: Sum: 15 (b takes default value 5)
}
```

### **b) Named Parameters** (Use curly braces `{}` and specify names)
```dart
void greet({String name = "Guest"}) {
  print("Hello, $name!");
}

void main() {
  greet();              // Hello, Guest!
  greet(name: "Alice"); // Hello, Alice!
}
```

### **c) Required Named Parameters** (Use `required` keyword)
```dart
void greet({required String name}) {
  print("Hello, $name!");
}

void main() {
  greet(name: "Alice"); // Works fine
  // greet();          // Error: The required parameter 'name' is missing
}
```

---

## **6. Arrow Functions (Short-Hand Functions)**
For single-expression functions, Dart allows the use of arrow `=>`.

```dart
int square(int num) => num * num;

void main() {
  print(square(4)); // Output: 16
}
```
This is equivalent to:
```dart
int square(int num) {
  return num * num;
}
```

---

## **7. Anonymous Functions (Lambda Functions)**
Dart allows functions without names, called **anonymous functions** or **lambda functions**.

```dart
var multiply = (int a, int b) {
  return a * b;
};

void main() {
  print(multiply(4, 5)); // Output: 20
}
```

---

## **8. First-Class Functions**
In Dart, functions are first-class citizens, meaning you can:
- Assign functions to variables
- Pass functions as parameters
- Return functions from other functions

### **Example: Assigning Function to a Variable**
```dart
void sayHello() {
  print("Hello!");
}

void main() {
  var func = sayHello; // Assigning function to a variable
  func();              // Calling function using variable
}
```

### **Example: Passing Function as a Parameter**
```dart
void operate(int a, int b, int Function(int, int) operation) {
  print(operation(a, b));
}

int multiply(int x, int y) => x * y;

void main() {
  operate(3, 4, multiply); // Output: 12
}
```

### **Example: Returning a Function**
```dart
Function getMultiplier(int factor) {
  return (int number) => number * factor;
}

void main() {
  var doubleIt = getMultiplier(2);
  print(doubleIt(5)); // Output: 10
}
```

---

## **9. Recursive Functions**
A function that calls itself is a **recursive function**.

### **Example: Factorial Calculation**
```dart
int factorial(int n) {
  if (n <= 1) return 1;
  return n * factorial(n - 1);
}

void main() {
  print(factorial(5)); // Output: 120
}
```

---

## **10. Higher-Order Functions**
Functions that take other functions as parameters or return functions are called **higher-order functions**.

```dart
void execute(Function action) {
  action();
}

void sayHi() {
  print("Hi there!");
}

void main() {
  execute(sayHi); // Output: Hi there!
}
```

## **11. Closures**
A **closure** is a function that retains access to variables from its surrounding scope even after the outer function has finished execution.

### **Example:**
```dart
Function counter() {
  int count = 0;
  return () {
    count++;
    print("Count: $count");
  };
}

void main() {
  var increment = counter();
  increment(); // Count: 1
  increment(); // Count: 2
}
```
