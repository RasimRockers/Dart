### Exception Handling in Dart

Dart provides robust exception handling using `try`, `catch`, `on`, and `finally` blocks to handle runtime errors gracefully. 

---

### **1. Handling Exceptions with `try` and `catch`**
The `try` block contains the code that may throw an exception, and the `catch` block handles the exception.

#### **Example: Using `try` and `catch`**
```dart
void main() {
  try {
    int result = 10 ~/ 0; // Division by zero exception
    print(result);
  } catch (e) {
    print("Exception caught: $e");
  }
}
```
#### **Output:**
```
Exception caught: IntegerDivisionByZeroException
```

---

### **2. Using `on` for Specific Exception Types**
If you know the type of exception, you can use `on` instead of `catch` to handle a specific exception type.

#### **Example: Handling Specific Exceptions**
```dart
void main() {
  try {
    int result = 10 ~/ 0;
    print(result);
  } on UnsupportedError {
    print("Cannot divide by zero!");
  }
}

```

---

### **3. Using `catch` with Stack Trace (`catch (e, s)`)**
If you want more details about the error, you can use a second parameter (`s`) to capture the stack trace.

#### **Example: Capturing Stack Trace**
```dart
void main() {
  try {
    List<int> numbers = [1, 2, 3];
    print(numbers[5]); // Accessing an out-of-bounds index
  } catch (e, s) {
    print("Exception caught: $e");
    print("Stack trace: $s");
  }
}
```

---

### **4. Using `finally`**
The `finally` block contains code that always executes, whether an exception occurs or not.

#### **Example: Using `finally`**
```dart
void main() {
  try {
    int result = 10 ~/ 0;
    print(result);
  } catch (e) {
    print("Exception caught: $e");
  } finally {
    print("This block always executes.");
  }
}
```
#### **Output:**
```
Exception caught: IntegerDivisionByZeroException
This block always executes.
```
or
```
Exception caught: Unsupported operation: Infinity
This block always executes.

```
---

### **5. Throwing Custom Exceptions**
You can define your own exception class by extending `Exception` and throw it using the `throw` keyword.

#### **Example: Custom Exception Handling**
```dart
class CustomException implements Exception {
  String message;
  CustomException(this.message);
  
  @override
  String toString() {
    return "CustomException: $message";
  }
}

void checkAge(int age) {
  if (age < 18) {
    throw CustomException("Age must be 18 or above.");
  } else {
    print("Access granted!");
  }
}

void main() {
  try {
    checkAge(16);
  } catch (e) {
    print(e);
  }
}
```
#### **Output:**
```
CustomException: Age must be 18 or above.
```

---

 
