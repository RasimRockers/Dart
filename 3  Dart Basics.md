## **Dart Basics** 


In Dart, variables are used to store data, and data types define the kind of data a variable can hold. Dart is a statically typed language, meaning every variable has a specific type.

## **Declaring Variables in Dart**
Dart provides two ways to declare variables:
1. **Explicit type declaration**  
   ```dart
   int age = 25;
   String name = "John";
   double price = 99.99;
   ```
2. **Using `var`, `final`, or `const`**  
   - `var` → Infers type at runtime  
   - `final` → Immutable variable, assigned only once  
   - `const` → Compile-time constant  

   ```dart
   var city = "Bangalore";  // Infers String
   final country = "India"; // Cannot be changed
   const PI = 3.14159;      // Compile-time constant
   ```

---

## **Data Types in Dart**
Dart provides several built-in data types:

### **1. Numbers**
- **`int`** → Stores whole numbers  
  ```dart
  int x = 10;
  ```
- **`double`** → Stores decimal numbers  
  ```dart
  double pi = 3.14;
  ```

### **2. Strings**
- Used for text representation  
  ```dart
  String name = "Alice";
  ```
- Multi-line string using triple quotes  
  ```dart
  String paragraph = '''This is 
  a multi-line string.''';
  ```

### **3. Booleans**
- Represents `true` or `false`  
  ```dart
  bool isActive = true;
  ```

### **4. Lists (Arrays)**
- Ordered collection of elements  
  ```dart
  List<int> numbers = [1, 2, 3, 4, 5];
  ```
- Using `var` or `List` without a type  
  ```dart
  var colors = ["red", "blue", "green"];
  ```

### **5. Maps (Key-Value Pairs)**
- Stores data in key-value pairs  
  ```dart
  Map<String, int> studentScores = {
    "Alice": 90,
    "Bob": 85
  };
  ```

### **6. Sets (Unique Collection)**
- Unordered collection of unique elements  
  ```dart
  Set<int> uniqueNumbers = {1, 2, 3, 4, 5};
  ```

### **7. Null Safety (`null` type)**
- By default, variables cannot be `null` unless specified with `?`  
  ```dart
  String? nullableString; // Can be null
  ```

## **8. `Dynamic` (Type Determined at Runtime)**
- The variable can hold **any type of value**.
- It **can change its type** at runtime.
- The compiler does **not enforce type safety**, meaning errors might appear at runtime instead of compile-time.

### **Example:**
```dart
void main() {
  dynamic value = "Hello"; // Initially a String
  print(value.length);     // (String property)

  value = 42;              // (Now an int)
  print(value + 8);        // (Mathematical operation)

  value = true;            // (Now a boolean)
}
```
🔹 **Key Point:** `dynamic` allows reassignment of different types and is resolved at runtime.

---

## **Example Program**
```dart
void main() {
  int age = 25;
  double height = 5.9;
  String name = "John";
  bool isStudent = false;
  List<String> hobbies = ["Reading", "Cycling"];
  Map<String, int> marks = {"Math": 95, "Science": 90};

  print("Name: $name, Age: $age, Height: $height");
  print("Student: $isStudent");
  print("Hobbies: $hobbies");
  print("Marks: $marks");
}
```
#### **Data Types in Dart**
| Type     | Description | Example |
|----------|------------|---------|
| int      | Integer numbers | `int x = 10;` |
| double   | Decimal numbers | `double pi = 3.14;` |
| String   | Text values | `String name = "Dart";` |
| bool     | True/False values | `bool isValid = true;` |
| var      | Type inferred by Dart | `var x = "Hello";` |
| dynamic  | Can hold any type | `dynamic y = 100; y = "Test";` |
| List     | Ordered collection | `List<int> numbers = [1,2,3];` |
| Set      | Unordered unique collection | `Set<int> ids = {101,102,103};` |
| Map      | Key-value pair collection | `Map<String, int> marks = {"Math": 90};` |

---

### **2. Constants and Final Variables**
Dart provides two ways to declare **constant values**:  
- `final` - Value is set **only once** and cannot be changed.  
- `const` - Value is **compile-time constant** (fixed at compile time).  

```dart
void main() {
  final String appName = "Dart App";
  const double pi = 3.1416;

  print("App Name: $appName, Pi: $pi");
}
```

> **Difference between `final` and `const`**:  
> - `final` can be assigned at runtime.  
> - `const` must be known at **compile time**.

---
## **Operators in Dart**
Operators in Dart are symbols used to perform operations on variables and values. Dart provides several types of operators:

---

## **1. Arithmetic Operators**
Used for mathematical operations.

| Operator | Description | Example (`a = 10, b = 5`) |
|----------|------------|--------------------------|
| `+` | Addition | `a + b` → `15` |
| `-` | Subtraction | `a - b` → `5` |
| `*` | Multiplication | `a * b` → `50` |
| `/` | Division (returns double) | `a / b` → `2.0` |
| `~/` | Integer Division | `a ~/ b` → `2` |
| `%` | Modulus (Remainder) | `a % b` → `0` |

### **Example:**
```dart
void main() {
  int a = 10, b = 5;
  print("Addition: ${a + b}");
  print("Subtraction: ${a - b}");
  print("Multiplication: ${a * b}");
  print("Division: ${a / b}");
  print("Integer Division: ${a ~/ b}");
  print("Modulus: ${a % b}");
}
```

---

## **2. Relational (Comparison) Operators**
Used to compare values, returning `true` or `false`.

| Operator | Description | Example (`a = 10, b = 5`) |
|----------|------------|--------------------------|
| `==` | Equal to | `a == b` → `false` |
| `!=` | Not equal to | `a != b` → `true` |
| `>` | Greater than | `a > b` → `true` |
| `<` | Less than | `a < b` → `false` |
| `>=` | Greater than or equal to | `a >= b` → `true` |
| `<=` | Less than or equal to | `a <= b` → `false` |

### **Example:**
```dart
void main() {
  int a = 10, b = 5;
  print(a == b);  // false
  print(a != b);  // true
  print(a > b);   // true
  print(a < b);   // false
  print(a >= b);  // true
  print(a <= b);  // false
}
```

---

## **3. Logical Operators**
Used to perform logical operations on Boolean values.


| Operator | Description     | Example (`x = true, y = false`) |
|----------|---------------|--------------------------|
| `&&`     | AND (Both true) | `x && y` → `false` |
| `\|\|`   | OR (Either true) | `x \|\| y` → `true`  |
| `!`      | NOT (Negation)  | `!x` → `false` |


### **Example:**
```dart
void main() {
  bool x = true, y = false;
  print(x && y);  // false
  print(x || y);  // true
  print(!x);      // false
}
```

---

## **4. Bitwise Operators**
Used to perform bit-level operations.

| Operator | Description | Example (`a = 2 (10 in binary), b = 3 (11 in binary)`) |
|----------|------------|------------------------------|
| `&` | Bitwise AND | `a & b` → `2` (10 & 11 = 10) |
| `\|` | Bitwise OR | `a \| b` → `3` (10 \| 11 = 11) |
| `^` | Bitwise XOR | `a ^ b` → `1` (10 ^ 11 = 01) |
| `~` | Bitwise NOT | `~a` → `-3` (~10 = -11) |
| `<<` | Left Shift | `a << 1` → `4` (10 << 1 = 100) |
| `>>` | Right Shift | `a >> 1` → `1` (10 >> 1 = 1) |

### **Example:**
```dart
void main() {
  int a = 2, b = 3;
  print(a & b);  // 2
  print(a | b);  // 3
  print(a ^ b);  // 1
  print(~a);     // -3
  print(a << 1); // 4
  print(a >> 1); // 1
}
```

---

## **5. Assignment Operators**
Used to assign values to variables.

| Operator | Example (`a = 10`) | Equivalent To |
|----------|-------------------|--------------|
| `=` | `a = 10` | `a = 10` |
| `+=` | `a += 5` | `a = a + 5` |
| `-=` | `a -= 5` | `a = a - 5` |
| `*=` | `a *= 2` | `a = a * 2` |
| `/=` | `a /= 2` | `a = a / 2` |
| `~/=` | `a ~/= 2` | `a = a ~/ 2` |
| `%=` | `a %= 3` | `a = a % 3` |

### **Example:**
```dart
void main() {
  int a = 10;
  a += 5; // a = a + 5 → 15
  a -= 2; // a = a - 2 → 13
  a *= 2; // a = a * 2 → 26
  a ~/= 2; // a = a ~/ 2 → 13
  print(a);
}
```

---

## **6. Conditional (Ternary) Operator**
Shortens `if-else` conditions.

| Operator | Syntax | Example |
|----------|--------|---------|
| `? :` | `condition ? expr1 : expr2` | `a > b ? "A is greater" : "B is greater"` |
| `??` | `expr1 ?? expr2` (Returns first non-null) | `name ?? "Guest"` |

### **Example:**
```dart
void main() {
  int a = 10, b = 5;
  String result = (a > b) ? "A is greater" : "B is greater";
  print(result); // A is greater

  String? name;
  print(name ?? "Guest"); // Guest
}
```

---

## **7. Type Test Operators**
Used to check and cast types.

| Operator | Description | Example |
|----------|------------|---------|
| `is` | Checks type | `x is int` |
| `is!` | Checks if NOT of type | `x is! String` |
| `as` | Typecast | `(x as String).length` |

### **Example:**
```dart
void main() {
  var x = 100;
  print(x is int);  // true
  print(x is! String); // true

  dynamic y = "Hello";
  print((y as String).length); // 5
}
```

---
# **Control Statements in Dart**
Control statements in Dart are used to manage the flow of execution in a program. They include **conditional statements, loop statements, and jump statements**.

---

# **1. Conditional Statements**
Conditional statements are used to execute a block of code based on conditions.

## **1.1 if Statement**
Executes a block of code only if the condition is `true`.

### **Syntax:**
```dart
if (condition) {
  // Code to execute if condition is true
}
```

### **Example:**
```dart
void main() {
  int age = 18;
  if (age >= 18) {
    print("You are eligible to vote.");
  }
}
```

---

## **1.2 if-else Statement**
Executes one block of code if the condition is `true` and another block if it is `false`.

### **Syntax:**
```dart
if (condition) {
  // Code if condition is true
} else {
  // Code if condition is false
}
```

### **Example:**
```dart
void main() {
  int number = 10;
  if (number % 2 == 0) {
    print("Even number");
  } else {
    print("Odd number");
  }
}
```

---

## **1.3 if-else if-else Statement**
Used when there are multiple conditions.

### **Syntax:**
```dart
if (condition1) {
  // Code if condition1 is true
} else if (condition2) {
  // Code if condition2 is true
} else {
  // Code if none of the conditions are true
}
```

### **Example:**
```dart
void main() {
  int marks = 85;
  if (marks >= 90) {
    print("Grade: A+");
  } else if (marks >= 80) {
    print("Grade: A");
  } else if (marks >= 70) {
    print("Grade: B");
  } else {
    print("Grade: C");
  }
}
```

## **1.4 switch-case Statement**
Used when multiple conditions are checked against a single value.

### **Syntax:**
```dart
switch (variable) {
  case value1:
    // Code block
    break;
  case value2:
    // Code block
    break;
  default:
    // Code block if no case matches
}
```

### **Example:**
```dart
void main() {
  int day = 3;
  switch (day) {
    case 1:
      print("Monday");
      break;
    case 2:
      print("Tuesday");
      break;
    case 3:
      print("Wednesday");
      break;
    default:
      print("Invalid day");
  }
}
```
🔹 **Note:** `break` is used to exit the switch statement after a case is matched.

---

# **2. Loop Statements**
Loops are used to execute a block of code multiple times.

---

## **2.1 for Loop**
Used when the number of iterations is known.

### **Syntax:**
```dart
for (initialization; condition; increment/decrement) {
  // Code to execute
}
```

### **Example:**
```dart
void main() {
  for (int i = 1; i <= 5; i++) {
    print("Number: $i");
  }
}
```

---

## **2.2 while Loop**
Used when the number of iterations is unknown but depends on a condition.

### **Syntax:**
```dart
while (condition) {
  // Code to execute
}
```

### **Example:**
```dart
void main() {
  int i = 1;
  while (i <= 5) {
    print("Hello Dart!");
    i++;
  }
}
```

---

## **2.3 do-while Loop**
Executes the code block **at least once** before checking the condition.

### **Syntax:**
```dart
do {
  // Code to execute
} while (condition);
```

### **Example:**
```dart
void main() {
  int i = 1;
  do {
    print("Number: $i");
    i++;
  } while (i <= 5);
}
```
🔹 **Difference between `while` and `do-while`?**  
`do-while` ensures at least one execution, even if the condition is false.

---

## **2.4 for-in Loop (Used for Lists/Sets)**
Used to iterate over elements in a collection.

### **Example:**
```dart
void main() {
  List<String> fruits = ["Apple", "Banana", "Mango"];
  for (String fruit in fruits) {
    print(fruit);
  }
}
```

---

## **2.5 forEach Loop (Lambda Expression)**
Used to iterate over collections using a function.

### **Example:**
```dart
void main() {
  List<int> numbers = [10, 20, 30, 40];
  numbers.forEach((num) {
    print(num);
  });
}
```

---

# **3. Jump Statements**
Jump statements control the flow by breaking or skipping iterations.

---

## **3.1 break Statement**
Used to exit a loop or switch statement.

### **Example:**
```dart
void main() {
  for (int i = 1; i <= 5; i++) {
    if (i == 3) {
      break; // Stops loop when i == 3
    }
    print(i);
  }
}
```
**Output:**
```
1
2
```

---

## **3.2 continue Statement**
Used to skip an iteration and continue with the next one.

### **Example:**
```dart
void main() {
  for (int i = 1; i <= 5; i++) {
    if (i == 3) {
      continue; // Skips iteration when i == 3
    }
    print(i);
  }
}
```
**Output:**
```
1
2
4
5
```

---

## **3.3 return Statement**
Used to exit from a function.

### **Example:**
```dart
int add(int a, int b) {
  return a + b;
}

void main() {
  int sum = add(10, 20);
  print("Sum: $sum");
}
```

