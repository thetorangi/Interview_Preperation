# 🐍 Complete Python Interview Questions Guide

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://python.org)
[![Interview Prep](https://img.shields.io/badge/Interview-Preparation-green.svg)](https://github.com)
[![Difficulty](https://img.shields.io/badge/Difficulty-Beginner%20to%20Expert-orange.svg)](https://github.com)

> A comprehensive collection of Python interview questions covering fundamental to advanced concepts. Perfect for developers preparing for technical interviews at top-tier companies.

## 📋 Table of Contents

- [🚀 Quick Start](#-quick-start)
- [📚 Fundamental Concepts](#-fundamental-concepts)
- [🔧 Intermediate Concepts](#-intermediate-concepts)
- [🎯 Advanced Concepts](#-advanced-concepts)
- [🏗️ Object-Oriented Programming](#️-object-oriented-programming)
- [🔄 Concurrency & Performance](#-concurrency--performance)
- [📊 Data Structures & Algorithms](#-data-structures--algorithms)
- [🌐 Web Development & Frameworks](#-web-development--frameworks)
- [📈 Data Analysis & Libraries](#-data-analysis--libraries)
- [🛠️ Tools & Best Practices](#️-tools--best-practices)

---

## 🚀 Quick Start

This guide contains **60+ carefully curated Python interview questions** with detailed explanations and practical examples. Each question includes:

- ✅ Clear, concise answers
- 💻 Code examples
- 🎯 Interview relevance
- 📝 Best practices

---

## 📚 Fundamental Concepts

### 1. 🔄 Mutable vs. Immutable Objects

**Question:** What's the difference between mutable and immutable objects in Python?

**Answer:**
- **Mutable objects** can be changed after creation (lists, dictionaries, sets)
- **Immutable objects** cannot be changed after creation (numbers, strings, tuples)

```python
# Mutable example
my_list = [1, 2, 3]
my_list.append(4)  # Modifies in-place
print(my_list)  # [1, 2, 3, 4]

# Immutable example
my_string = "Hello"
my_string += " World"  # Creates new string object
```

**Interview Relevance:** Understanding mutability is crucial for avoiding bugs and understanding Python's memory model.

---

### 2. 📦 *args and **kwargs

**Question:** Explain *args and **kwargs in Python functions.

**Answer:**
- `*args` collects arbitrary positional arguments into a tuple
- `**kwargs` collects arbitrary keyword arguments into a dictionary

```python
def example_function(*args, **kwargs):
    print("Positional args (tuple):", args)
    print("Keyword args (dict):", kwargs)

example_function(1, 2, 'hello', name='Alice', age=30)
# Output:
# Positional args (tuple): (1, 2, 'hello')
# Keyword args (dict): {'name': 'Alice', 'age': 30}
```

---

### 3. 📝 Lists vs. Tuples

**Question:** What are the key differences between lists and tuples?

**Answer:**

| Feature | List | Tuple |
|---------|------|-------|
| Mutability | ✅ Mutable | ❌ Immutable |
| Syntax | `[1, 2, 3]` | `(1, 2, 3)` |
| Performance | Slower | Faster |
| Use Case | Dynamic data | Fixed data |
| Hashable | ❌ No | ✅ Yes |

---

### 4. 🎯 PEP 8 Style Guide

**Question:** What is PEP 8 and why is it important?

**Answer:**
PEP 8 is Python's official style guide providing conventions for writing clean, readable code:

- **Indentation:** 4 spaces per level
- **Line Length:** 79 characters max
- **Naming:** `snake_case` for variables/functions, `CamelCase` for classes
- **Imports:** Standard library first, then third-party, then local

---

### 5. 🌍 Global vs. Local Variables

**Question:** Explain the difference between global and local variables.

**Answer:**

```python
global_var = 10  # Global variable

def my_function():
    local_var = 5  # Local variable
    global global_var
    global_var += 1  # Modify global variable
    print(f"Local: {local_var}, Global: {global_var}")

my_function()
print(f"Global outside: {global_var}")
```

---

### 6. 📁 Python Modules

**Question:** What are modules in Python?

**Answer:**
A **module** is a Python file containing functions, classes, and variables. Modules help organize code and enable reusability.

```python
# my_module.py
def greet(name):
    return f"Hello, {name}!"

PI = 3.14159

# main.py
import my_module
print(my_module.greet("World"))
print(my_module.PI)
```

---

### 7. 🏗️ __init__ Method

**Question:** What is the purpose of __init__ in Python classes?

**Answer:**
`__init__` is a special method (constructor) automatically called when creating a new instance of a class.

```python
class Dog:
    def __init__(self, name, breed):
        self.name = name      # Initialize instance attributes
        self.breed = breed

my_dog = Dog("Buddy", "Golden Retriever")
print(my_dog.name)  # Output: Buddy
```

---

### 8. 📄 .pyc Files

**Question:** What are .pyc files?

**Answer:**
`.pyc` files are **bytecode compiled files** created by Python interpreter when importing `.py` files. They contain platform-independent bytecode that speeds up subsequent imports.

---

### 9. 💬 Docstrings

**Question:** What are docstrings and how are they used?

**Answer:**
**Docstrings** are multi-line strings used to document modules, classes, functions, or methods.

```python
def calculate_area(radius):
    """
    Calculate the area of a circle.
    
    Args:
        radius (float): The radius of the circle
        
    Returns:
        float: The area of the circle
    """
    return 3.14159 * radius ** 2

print(help(calculate_area))  # Access docstring
```

---

### 10. 🔄 Variable Swapping

**Question:** How do you swap variables in Python?

**Answer:**
Python provides elegant tuple packing/unpacking for swapping:

```python
a = 5
b = 10
a, b = b, a  # Pythonic way to swap
print(f"a: {a}, b: {b}")  # Output: a: 10, b: 5
```

---

## 🔧 Intermediate Concepts

### 11. 🎛️ break and continue

**Question:** Explain the difference between break and continue statements.

**Answer:**

```python
for i in range(5):
    if i == 2:
        continue  # Skip iteration when i=2
    if i == 4:
        break     # Exit loop when i=4
    print(i)
# Output: 0, 1, 3
```

- `break`: Exits the entire loop
- `continue`: Skips current iteration, continues with next

---

### 12. 📦 PyPI (Python Package Index)

**Question:** What is PyPI?

**Answer:**
**PyPI** is the official repository for third-party Python packages. Developers can:
- Publish packages: `python setup.py sdist upload`
- Install packages: `pip install package_name`
- Search packages: `pip search keyword`

---

### 13. 🗂️ Python Data Structures

**Question:** What are Python's built-in data structures?

**Answer:**

| Type | Example | Mutable | Ordered | Use Case |
|------|---------|---------|---------|----------|
| `int` | `42` | ❌ | N/A | Numbers |
| `str` | `"Hello"` | ❌ | ✅ | Text |
| `list` | `[1, 2, 3]` | ✅ | ✅ | Dynamic arrays |
| `tuple` | `(1, 2, 3)` | ❌ | ✅ | Fixed records |
| `dict` | `{"a": 1}` | ✅ | ✅* | Key-value pairs |
| `set` | `{1, 2, 3}` | ✅ | ❌ | Unique items |

*Ordered since Python 3.7

---

### 14. 🔍 Dictionary Iteration

**Question:** How do you iterate over a dictionary?

**Answer:**

```python
my_dict = {'name': 'Alice', 'age': 30, 'city': 'NYC'}

# Iterate over keys (default)
for key in my_dict:
    print(key)

# Iterate over values
for value in my_dict.values():
    print(value)

# Iterate over key-value pairs (most common)
for key, value in my_dict.items():
    print(f"{key}: {value}")
```

---

### 15. 🔤 Count Vowels Challenge

**Question:** Write a function to count vowels in a string.

**Answer:**

```python
def count_vowels(text):
    vowels = "aeiouAEIOU"
    return sum(1 for char in text if char in vowels)

# Alternative using list comprehension
def count_vowels_alt(text):
    vowels = "aeiouAEIOU"
    return len([char for char in text if char in vowels])

print(count_vowels("Hello World"))  # Output: 3
```

---

### 16. ➕ Adding to Dictionaries

**Question:** How do you add elements to a dictionary?

**Answer:**

```python
my_dict = {'name': 'Alice'}

# Add single key-value pair
my_dict['age'] = 30

# Update existing key
my_dict['name'] = 'Bob'

# Add multiple items using update()
my_dict.update({'city': 'NYC', 'job': 'Engineer'})

# Using dict comprehension
new_items = {f'key_{i}': i for i in range(3)}
my_dict.update(new_items)
```

---

### 17. ⚠️ UnboundLocalError

**Question:** What causes UnboundLocalError?

**Answer:**
Occurs when trying to read a local variable before assignment in a function where that variable also exists globally.

```python
count = 0  # Global variable

def increment_wrong():
    print(count)  # This would cause UnboundLocalError
    count = 1     # Python treats 'count' as local

def increment_correct():
    global count
    count += 1
    print(count)

increment_correct()  # Works correctly
```

---

### 18. 📖 Reading N Characters

**Question:** How do you read n characters from a file?

**Answer:**

```python
def read_n_chars(filepath, n):
    try:
        with open(filepath, 'r', encoding='utf-8') as file:
            return file.read(n)
    except FileNotFoundError:
        return "File not found"
    except IOError:
        return "Error reading file"

# Example usage
content = read_n_chars('example.txt', 100)
print(content)
```

---

### 19. 🔢 Fibonacci Sequence

**Question:** Implement Fibonacci sequence generation.

**Answer:**

```python
# Iterative approach (efficient)
def fibonacci_iterative(n):
    if n <= 1:
        return n
    a, b = 0, 1
    for _ in range(2, n + 1):
        a, b = b, a + b
    return b

# Generator approach (memory efficient)
def fibonacci_generator(n):
    a, b = 0, 1
    for _ in range(n):
        yield a
        a, b = b, a + b

# Usage
print([fibonacci_iterative(i) for i in range(10)])
print(list(fibonacci_generator(10)))
```

---

### 20. 🔗 Understanding 'self'

**Question:** What is 'self' in Python classes?

**Answer:**
`self` refers to the instance of the class and allows access to instance attributes and methods.

```python
class Car:
    def __init__(self, make, model):
        self.make = make      # Instance attribute
        self.model = model    # Instance attribute
    
    def get_info(self):
        return f"{self.make} {self.model}"  # Access via self

my_car = Car("Toyota", "Camry")
print(my_car.get_info())  # Toyota Camry
```

---

## 🎯 Advanced Concepts

### 21. 🔧 Lambda Functions and Sorting

**Question:** How do you use lambda functions with sorting?

**Answer:**

```python
students = [('Alice', 85), ('Bob', 90), ('Charlie', 78)]

# Sort by grade (second element)
sorted_by_grade = sorted(students, key=lambda x: x[1], reverse=True)
print(sorted_by_grade)  # [('Bob', 90), ('Alice', 85), ('Charlie', 78)]

# Sort by name length
sorted_by_name_len = sorted(students, key=lambda x: len(x[0]))
print(sorted_by_name_len)

# Multiple criteria sorting
data = [('Alice', 25, 85), ('Bob', 30, 90), ('Alice', 22, 95)]
sorted_data = sorted(data, key=lambda x: (x[0], -x[2]))  # Name asc, grade desc
```

---

### 22. ⚙️ Function Parameter Defaults

**Question:** How do default parameters work in Python?

**Answer:**

```python
# Safe default parameters
def greet(name, greeting="Hello", punctuation="!"):
    return f"{greeting}, {name}{punctuation}"

print(greet("Alice"))                    # Hello, Alice!
print(greet("Bob", "Hi"))               # Hi, Bob!
print(greet("Charlie", "Hey", "?"))     # Hey, Charlie?

# Dangerous: Mutable default arguments
def add_item_wrong(item, target_list=[]):  # DON'T DO THIS
    target_list.append(item)
    return target_list

# Correct approach
def add_item_correct(item, target_list=None):
    if target_list is None:
        target_list = []
    target_list.append(item)
    return target_list
```

---

### 23. 🏛️ Static and Class Methods

**Question:** Explain @staticmethod and @classmethod decorators.

**Answer:**

```python
class MathUtils:
    class_variable = "I'm shared by all instances"
    
    def __init__(self, value):
        self.value = value
    
    @staticmethod
    def add_numbers(a, b):
        """Static method - no access to self or cls"""
        return a + b
    
    @classmethod
    def create_from_string(cls, string_value):
        """Class method - alternative constructor"""
        return cls(int(string_value))
    
    @classmethod
    def get_class_variable(cls):
        """Class method - access class variables"""
        return cls.class_variable

# Usage
print(MathUtils.add_numbers(5, 3))           # 8 (static)
obj = MathUtils.create_from_string("42")     # Class method as constructor
print(obj.value)                             # 42
print(MathUtils.get_class_variable())        # I'm shared by all instances
```

---

### 24. 🔍 Module Introspection

**Question:** How do you find functions and attributes in a module?

**Answer:**

```python
import math
import inspect

# List all attributes and methods
print("All attributes:", dir(math))

# Get only functions using inspect
functions = [(name, obj) for name, obj in inspect.getmembers(math) 
             if inspect.isfunction(obj)]
print("Functions:", [name for name, _ in functions])

# Get help for specific function
print(help(math.sqrt))

# Check if attribute exists
if hasattr(math, 'pi'):
    print(f"Pi value: {math.pi}")
```

---

### 25. 🧠 Memory Management

**Question:** How does Python handle memory management?

**Answer:**
Python uses **automatic memory management** through:

1. **Reference Counting**: Objects track reference count; deallocated when count reaches 0
2. **Garbage Collection**: Handles circular references using generational collection
3. **Memory Pool**: Pre-allocates memory for small objects

```python
import sys
import gc

# Check reference count
my_list = [1, 2, 3]
print(sys.getrefcount(my_list))  # Shows reference count

# Force garbage collection
gc.collect()

# Memory profiling example
def memory_heavy_function():
    large_list = list(range(1000000))
    return len(large_list)

result = memory_heavy_function()
# Large list gets garbage collected automatically
```

---

### 26. 🔄 For-Else Clause

**Question:** Explain the else clause in for loops.

**Answer:**
The `else` clause executes only if the loop completes normally (not terminated by `break`).

```python
# Example: Finding if a number is prime
def is_prime(n):
    if n < 2:
        return False
    
    for i in range(2, int(n**0.5) + 1):
        if n % i == 0:
            print(f"{n} is divisible by {i}")
            break
    else:
        # This executes only if no break occurred
        print(f"{n} is prime")
        return True
    
    return False

is_prime(17)  # 17 is prime (else executes)
is_prime(15)  # 15 is divisible by 3 (else doesn't execute)
```

---

### 27. 🌟 Context Managers

**Question:** What are context managers and how do you use the 'with' statement?

**Answer:**
Context managers ensure proper resource management using `__enter__` and `__exit__` methods.

```python
# Built-in context manager
with open('file.txt', 'r') as f:
    content = f.read()
# File automatically closed

# Custom context manager using class
class DatabaseConnection:
    def __enter__(self):
        print("Connecting to database...")
        return self
    
    def __exit__(self, exc_type, exc_val, exc_tb):
        print("Closing database connection...")
        return False  # Don't suppress exceptions

# Custom context manager using contextlib
from contextlib import contextmanager

@contextmanager
def timer():
    import time
    start = time.time()
    print("Timer started")
    try:
        yield
    finally:
        end = time.time()
        print(f"Elapsed time: {end - start:.2f} seconds")

# Usage
with timer():
    time.sleep(1)
```

---

### 28. 🎯 Pass by Reference vs. Value

**Question:** How does Python handle argument passing?

**Answer:**
Python uses **"pass by object reference"** (or "call by sharing").

```python
def modify_values(num, lst, string):
    # Immutable objects: creates new objects
    num = num + 10
    string = string + " modified"
    
    # Mutable objects: modifies original
    lst.append(4)
    lst[0] = 999
    
    print(f"Inside function - num: {num}, string: {string}, lst: {lst}")

# Original values
original_num = 5
original_string = "hello"
original_list = [1, 2, 3]

modify_values(original_num, original_list, original_string)

print(f"Outside function - num: {original_num}")      # 5 (unchanged)
print(f"Outside function - string: {original_string}") # "hello" (unchanged)
print(f"Outside function - list: {original_list}")    # [999, 2, 3, 4] (changed!)
```

---

### 29. 🔒 Closures

**Question:** What are closures in Python?

**Answer:**
A **closure** is a nested function that captures and remembers values from its enclosing scope.

```python
def outer_function(x):
    # Enclosing scope variable
    multiplier = x
    
    def inner_function(y):
        # Inner function "closes over" multiplier
        return multiplier * y
    
    return inner_function

# Create closures
multiply_by_5 = outer_function(5)
multiply_by_10 = outer_function(10)

print(multiply_by_5(3))   # 15 (5 * 3)
print(multiply_by_10(3))  # 30 (10 * 3)

# Practical example: Event handlers
def make_event_handler(name):
    def handler(event):
        print(f"Handling {event} for {name}")
    return handler

button_handler = make_event_handler("Submit Button")
button_handler("click")  # Handling click for Submit Button
```

---

### 30. 🔄 Iterator Protocol

**Question:** Explain Python's iterator protocol.

**Answer:**
Objects implementing `__iter__()` and `__next__()` methods follow the iterator protocol.

```python
class CountDown:
    def __init__(self, start):
        self.start = start
    
    def __iter__(self):
        return self
    
    def __next__(self):
        if self.start <= 0:
            raise StopIteration
        self.start -= 1
        return self.start + 1

# Usage
countdown = CountDown(3)
for num in countdown:
    print(num)  # Prints: 3, 2, 1

# Manual iteration
countdown2 = CountDown(2)
iterator = iter(countdown2)
print(next(iterator))  # 2
print(next(iterator))  # 1
# print(next(iterator))  # Raises StopIteration
```

---

### 31. 🏷️ __name__ Variable

**Question:** What is the purpose of __name__ in Python?

**Answer:**
`__name__` is a built-in variable that indicates how a Python file is being executed.

```python
# my_module.py
def main():
    print("Running main function")

def helper_function():
    print("This is a helper function")

if __name__ == "__main__":
    # This code runs only when script is executed directly
    print("Script is being run directly")
    main()
else:
    # This code runs when script is imported
    print(f"Module {__name__} is being imported")

# When run directly: __name__ == "__main__"
# When imported: __name__ == "my_module"
```

---

### 32. 📝 str vs. bytes

**Question:** What's the difference between str and bytes?

**Answer:**

```python
# str: Unicode text data
text_string = "Hello, 世界! 🐍"
print(type(text_string))  # <class 'str'>

# bytes: Binary data
binary_data = text_string.encode('utf-8')
print(type(binary_data))  # <class 'bytes'>
print(binary_data)        # b'Hello, \xe4\xb8\x96\xe7\x95\x8c! \xf0\x9f\x90\x8d'

# Convert back
decoded_string = binary_data.decode('utf-8')
print(decoded_string)     # Hello, 世界! 🐍

# Practical usage
def save_text_to_file(text, filename):
    with open(filename, 'wb') as f:  # Write binary mode
        f.write(text.encode('utf-8'))

def read_text_from_file(filename):
    with open(filename, 'rb') as f:  # Read binary mode
        return f.read().decode('utf-8')
```

---

### 33. ⚡ Operator Overloading

**Question:** How do you implement operator overloading?

**Answer:**

```python
class Vector:
    def __init__(self, x, y):
        self.x = x
        self.y = y
    
    def __add__(self, other):
        """Overload + operator"""
        return Vector(self.x + other.x, self.y + other.y)
    
    def __sub__(self, other):
        """Overload - operator"""
        return Vector(self.x - other.x, self.y - other.y)
    
    def __mul__(self, scalar):
        """Overload * operator"""
        return Vector(self.x * scalar, self.y * scalar)
    
    def __eq__(self, other):
        """Overload == operator"""
        return self.x == other.x and self.y == other.y
    
    def __str__(self):
        """String representation"""
        return f"Vector({self.x}, {self.y})"
    
    def __repr__(self):
        """Developer representation"""
        return f"Vector({self.x}, {self.y})"

# Usage
v1 = Vector(2, 3)
v2 = Vector(1, 4)

print(v1 + v2)    # Vector(3, 7)
print(v1 - v2)    # Vector(1, -1)
print(v1 * 3)     # Vector(6, 9)
print(v1 == v2)   # False
```

---

### 34. 🔢 Processing Space-Separated Numbers

**Question:** How do you parse whitespace-separated numbers?

**Answer:**

```python
def parse_numbers(input_string, number_type=int):
    """Parse space-separated numbers from string"""
    try:
        numbers = [number_type(x) for x in input_string.split()]
        return numbers
    except ValueError as e:
        print(f"Error parsing numbers: {e}")
        return []

# Examples
input_data = "10 20 30 40 50"
integers = parse_numbers(input_data, int)
print(f"Integers: {integers}")

float_data = "3.14 2.71 1.41 0.57"
floats = parse_numbers(float_data, float)
print(f"Floats: {floats}")

# Interactive version
def get_numbers_from_user():
    user_input = input("Enter space-separated numbers: ")
    return parse_numbers(user_input, float)
```

---

### 35. 🔄 Palindrome Detection

**Question:** How do you check if a string is a palindrome?

**Answer:**

```python
def is_palindrome_basic(s):
    """Basic palindrome check"""
    return s == s[::-1]

def is_palindrome_advanced(s):
    """Advanced palindrome check (ignores case, spaces, punctuation)"""
    # Keep only alphanumeric characters and convert to lowercase
    cleaned = ''.join(char.lower() for char in s if char.isalnum())
    return cleaned == cleaned[::-1]

def is_palindrome_efficient(s):
    """Memory-efficient two-pointer approach"""
    left, right = 0, len(s) - 1
    while left < right:
        if s[left] != s[right]:
            return False
        left += 1
        right -= 1
    return True

# Test cases
test_cases = [
    "racecar",
    "A man a plan a canal Panama",
    "race a car",
    "hello",
    "Madam",
    ""
]

for test in test_cases:
    print(f"'{test}' -> Basic: {is_palindrome_basic(test)}, "
          f"Advanced: {is_palindrome_advanced(test)}")
```

---

### 36. 📊 Mean Square Error

**Question:** Implement Mean Square Error calculation.

**Answer:**

```python
def mean_squared_error(actual, predicted):
    """
    Calculate Mean Squared Error between actual and predicted values.
    
    Formula: MSE = (1/n) * Σ(yi - ŷi)²
    """
    if len(actual) != len(predicted):
        raise ValueError("Arrays must have same length")
    
    squared_errors = [(a - p) ** 2 for a, p in zip(actual, predicted)]
    return sum(squared_errors) / len(actual)

def root_mean_squared_error(actual, predicted):
    """Calculate Root Mean Square Error"""
    return mean_squared_error(actual, predicted) ** 0.5

def mean_absolute_error(actual, predicted):
    """Calculate Mean Absolute Error"""
    if len(actual) != len(predicted):
        raise ValueError("Arrays must have same length")
    
    absolute_errors = [abs(a - p) for a, p in zip(actual, predicted)]
    return sum(absolute_errors) / len(actual)

# Example usage
y_true = [3, -0.5, 2, 7, 4.2]
y_pred = [2.5, 0.0, 2.1, 7.8, 4.0]

mse = mean_squared_error(y_true, y_pred)
rmse = root_mean_squared_error(y_true, y_pred)
mae = mean_absolute_error(y_true, y_pred)

print(f"MSE: {mse:.4f}")
print(f"RMSE: {rmse:.4f}")
print(f"MAE: {mae:.4f}")
```

---

### 37. 🏷️ Type Annotations

**Question:** How do you use type hints in Python?

**Answer:**

```python
from typing import List, Dict, Union, Optional, Callable, Tuple

def process_data(
    names: List[str], 
    ages: Dict[str, int], 
    weight: Optional[float] = None
) -> Dict[str, Union[str, int, float]]:
    """Process user data with type hints"""
    result: Dict[str, Union[str, int, float]] = {}
    
    for name in names:
        result[name] = ages.get(name, 0)
        if weight is not None:
            result[f"{name}_weight"] = weight
    
    return result

# Complex type annotations
def apply_operation(
    data: List[int], 
    operation: Callable[[int], int]
) -> List[int]:
    """Apply function to each element"""
    return [operation(x) for x in data]

# Usage with lambda
numbers = [1, 2, 3, 4, 5]
squared = apply_operation(numbers, lambda x: x ** 2)
print(squared)  # [1, 4, 9, 16, 25]

# Variable annotations
user_name: str = "Alice"
user_scores: List[float] = [85.5, 92.0, 78.5]
metadata: Dict[str, Union[str, int]] = {"version": 1, "author": "Bob"}
```

---

### 38. 📁 Recursive Directory Listing

**Question:** How do you recursively list directory contents?

**Answer:**

```python
import os
from pathlib import Path

def list_directory_os_walk(start_path: str) -> None:
    """List directory contents using os.walk"""
    print(f"Listing contents of: {start_path}")
    
    for root, dirs, files in os.walk(start_path):
        level = root.replace(start_path, '').count(os.sep)
        indent = '  ' * level
        print(f'{indent}{os.path.basename(root)}/')
        
        sub_indent = '  ' * (level + 1)
        for file in files:
            print(f'{sub_indent}{file}')

def list_directory_pathlib(path: str) -> List[Path]:
    """List directory contents using pathlib (modern approach)"""
    directory = Path(path)
    if not directory.is_dir():
        raise ValueError(f"{path} is not a valid directory")
    
    all_items = []
    for item in directory.rglob('*'):  # Recursive glob
        all_items.append(item)
    
    return all_items

# Example usage
try:
    items = list_directory_pathlib('.')
    for item in items[:10]:  # Show first 10 items
        print(f"{'Dir' if item.is_dir() else 'File'}: {item}")
except ValueError as e:
    print(f"Error: {e}")
```

---

### 39. String-Only Arguments (Positional-Only)

**Question:** How do positional-only arguments work in Python 3.8+?

**Answer:**

```python
def create_point(x, y, /):
    """
    Create a point with positional-only arguments.
    The '/' indicates that x and y must be passed positionally.
    """
    return {"x": x, "y": y}

def mixed_arguments(pos_only, /, normal, *, kwd_only):
    """
    Demonstrate different argument types:
    - pos_only: must be positional
    - normal: can be positional or keyword
    - kwd_only: must be keyword (after *)
    """
    return f"pos_only={pos_only}, normal={normal}, kwd_only={kwd_only}"

# Valid calls
point1 = create_point(10, 20)  # OK
# point2 = create_point(x=10, y=20)  # TypeError!

result = mixed_arguments(1, 2, kwd_only=3)  # OK
result = mixed_arguments(1, normal=2, kwd_only=3)  # OK
# result = mixed_arguments(pos_only=1, normal=2, kwd_only=3)  # TypeError!
```

---

### 40. Class Attributes vs Instance Attributes

**Question:** What's the difference between class and instance attributes?

**Answer:**

```python
class Vehicle:
    # Class attributes (shared by all instances)
    wheels = 4
    vehicle_count = 0
    
    def __init__(self, make, model):
        # Instance attributes (unique to each instance)
        self.make = make
        self.model = model
        Vehicle.vehicle_count += 1  # Modify class attribute
    
    def get_info(self):
        return f"{self.make} {self.model} with {self.wheels} wheels"
    
    @classmethod
    def get_vehicle_count(cls):
        return cls.vehicle_count

# Usage examples
car1 = Vehicle("Toyota", "Camry")
car2 = Vehicle("Honda", "Civic")

print(f"Total vehicles: {Vehicle.get_vehicle_count()}")  # 2

# Modifying class attribute affects all instances
Vehicle.wheels = 6
print(car1.get_info())  # Toyota Camry with 6 wheels
print(car2.get_info())  # Honda Civic with 6 wheels

# Instance can shadow class attribute
car1.wheels = 8  # Creates instance attribute
print(car1.get_info())  # Toyota Camry with 8 wheels
print(car2.get_info())  # Honda Civic with 6 wheels
```

---

### 41. Global Interpreter Lock (GIL)

**Question:** What is the GIL and how does it affect Python programs?

**Answer:**
The **GIL** is a mutex that prevents multiple native threads from executing Python bytecodes simultaneously.

```python
import threading
import time
from multiprocessing import Process, cpu_count

def cpu_bound_task(n):
    """CPU-intensive task"""
    total = 0
    for i in range(n):
        total += i * i
    return total

def io_bound_task():
    """I/O-intensive task"""
    time.sleep(1)
    return "Task completed"

# GIL Impact on CPU-bound tasks
def test_threading_cpu_bound():
    """Threading doesn't help with CPU-bound tasks due to GIL"""
    start_time = time.time()
    
    threads = []
    for _ in range(4):
        t = threading.Thread(target=cpu_bound_task, args=(1000000,))
        threads.append(t)
        t.start()
    
    for t in threads:
        t.join()
    
    return time.time() - start_time

def test_multiprocessing_cpu_bound():
    """Multiprocessing bypasses GIL"""
    start_time = time.time()
    
    processes = []
    for _ in range(4):
        p = Process(target=cpu_bound_task, args=(1000000,))
        processes.append(p)
        p.start()
    
    for p in processes:
        p.join()
    
    return time.time() - start_time

# GIL doesn't affect I/O-bound tasks much
def test_threading_io_bound():
    """Threading helps with I/O-bound tasks"""
    start_time = time.time()
    
    threads = []
    for _ in range(4):
        t = threading.Thread(target=io_bound_task)
        threads.append(t)
        t.start()
    
    for t in threads:
        t.join()
    
    return time.time() - start_time

print(f"CPU cores available: {cpu_count()}")
print(f"Threading (CPU-bound): {test_threading_cpu_bound():.2f}s")
print(f"Multiprocessing (CPU-bound): {test_multiprocessing_cpu_bound():.2f}s")
print(f"Threading (I/O-bound): {test_threading_io_bound():.2f}s")
```

---

### 42. Apply Function to Directory

**Question:** How do you apply a function to all files in a directory?

**Answer:**

```python
import os
from pathlib import Path
from typing import Callable, List

def apply_to_files(directory: str, func: Callable, 
                  file_extensions: List[str] = None, 
                  recursive: bool = True):
    """Apply a function to all files in a directory"""
    path = Path(directory)
    
    if not path.exists():
        raise FileNotFoundError(f"Directory {directory} not found")
    
    pattern = '**/*' if recursive else '*'
    
    for file_path in path.glob(pattern):
        if file_path.is_file():
            # Filter by extension if specified
            if file_extensions and file_path.suffix.lower() not in file_extensions:
                continue
            
            try:
                func(file_path)
            except Exception as e:
                print(f"Error processing {file_path}: {e}")

# Example functions to apply
def count_lines(file_path: Path):
    """Count lines in a text file"""
    try:
        with open(file_path, 'r', encoding='utf-8') as f:
            line_count = sum(1 for _ in f)
            print(f"{file_path.name}: {line_count} lines")
    except UnicodeDecodeError:
        print(f"{file_path.name}: Binary file, skipping")

def get_file_size(file_path: Path):
    """Get file size in bytes"""
    size = file_path.stat().st_size
    print(f"{file_path.name}: {size:,} bytes")

def backup_file(file_path: Path):
    """Create a backup copy"""
    backup_path = file_path.with_suffix(file_path.suffix + '.backup')
    backup_path.write_bytes(file_path.read_bytes())
    print(f"Backed up: {file_path.name}")

# Usage examples
if os.path.exists('.'):
    print("Counting lines in Python files:")
    apply_to_files('.', count_lines, ['.py'], recursive=False)
    
    print("\nFile sizes:")
    apply_to_files('.', get_file_size, recursive=False)
```

---

### 43. 'is' vs '==' Comparison

**Question:** What's the difference between 'is' and '==' operators?

**Answer:**

```python
# '==' checks value equality
# 'is' checks identity (same object in memory)

# Example 1: Integers (Python caches small integers)
a = 5
b = 5
print(f"a == b: {a == b}")  # True (same value)
print(f"a is b: {a is b}")  # True (same object due to caching)

# Example 2: Larger integers (not cached)
x = 1000
y = 1000
print(f"x == y: {x == y}")  # True (same value)
print(f"x is y: {x is y}")  # False (different objects)

# Example 3: Lists
list1 = [1, 2, 3]
list2 = [1, 2, 3]
list3 = list1

print(f"list1 == list2: {list1 == list2}")  # True (same content)
print(f"list1 is list2: {list1 is list2}")  # False (different objects)
print(f"list1 is list3: {list1 is list3}")  # True (same object)

# Example 4: None (always use 'is' with None)
value = None
print(f"value == None: {value == None}")  # True, but not recommended
print(f"value is None: {value is None}")  # True, recommended

# Example 5: Custom class with __eq__ override
class Person:
    def __init__(self, name):
        self.name = name
    
    def __eq__(self, other):
        if isinstance(other, Person):
            return self.name == other.name
        return False

person1 = Person("Alice")
person2 = Person("Alice")
person3 = person1

print(f"person1 == person2: {person1 == person2}")  # True (same name)
print(f"person1 is person2: {person1 is person2}")  # False (different objects)
print(f"person1 is person3: {person1 is person3}")  # True (same object)

# Memory addresses
print(f"id(person1): {id(person1)}")
print(f"id(person2): {id(person2)}")
print(f"id(person3): {id(person3)}")
```

---

## Object-Oriented Programming

### 44. Rebuild itertools.chain()

**Question:** How would you implement itertools.chain()?

**Answer:**

```python
def my_chain(*iterables):
    """
    Recreation of itertools.chain() - flattens multiple iterables
    into a single iterator.
    """
    for iterable in iterables:
        for item in iterable:
            yield item

# Alternative implementation using yield from (Python 3.3+)
def my_chain_modern(*iterables):
    """Modern implementation using yield from"""
    for iterable in iterables:
        yield from iterable

# Usage examples
list1 = [1, 2, 3]
tuple1 = ('a', 'b', 'c')
string1 = "xyz"

# Using our implementation
chained = my_chain(list1, tuple1, string1)
print(list(chained))  # [1, 2, 3, 'a', 'b', 'c', 'x', 'y', 'z']

# Compare with built-in
import itertools
builtin_chain = itertools.chain(list1, tuple1, string1)
print(list(builtin_chain))  # Same result

# Advanced usage: chain.from_iterable equivalent
def chain_from_iterable(iterable):
    """Equivalent to itertools.chain.from_iterable()"""
    for sub_iterable in iterable:
        yield from sub_iterable

nested_lists = [[1, 2], [3, 4], [5, 6]]
flattened = chain_from_iterable(nested_lists)
print(list(flattened))  # [1, 2, 3, 4, 5, 6]
```

---

### 45. Rebuild range() as Generator

**Question:** How would you implement range() as a generator?

**Answer:**

```python
def my_range(start, stop=None, step=1):
    """
    Generator implementation of range() function.
    Supports all range() functionality: start, stop, step.
    """
    # Handle single argument case: range(5) -> range(0, 5, 1)
    if stop is None:
        start, stop = 0, start
    
    # Validate step
    if step == 0:
        raise ValueError("range() arg 3 must not be zero")
    
    # Generate values
    if step > 0:
        while start < stop:
            yield start
            start += step
    else:  # step < 0
        while start > stop:
            yield start
            start += step

# Test cases
print("my_range(5):", list(my_range(5)))
print("my_range(2, 8):", list(my_range(2, 8)))
print("my_range(0, 10, 2):", list(my_range(0, 10, 2)))
print("my_range(10, 0, -2):", list(my_range(10, 0, -2)))
print("my_range(5, 5):", list(my_range(5, 5)))  # Empty range

# Memory efficiency demonstration
def memory_comparison():
    """Show memory efficiency of generator vs list"""
    import sys
    
    # Built-in range (returns range object, not list in Python 3)
    builtin_range = range(1000000)
    custom_range = my_range(1000000)
    list_version = list(range(1000000))
    
    print(f"Built-in range object size: {sys.getsizeof(builtin_range)} bytes")
    print(f"Custom generator size: {sys.getsizeof(custom_range)} bytes")
    print(f"List version size: {sys.getsizeof(list_version)} bytes")

memory_comparison()
```

---

### 46. Full-Name Property

**Question:** Implement a Person class with a full_name property.

**Answer:**

```python
class Person:
    def __init__(self, first_name: str, last_name: str):
        self._first_name = first_name
        self._last_name = last_name
    
    @property
    def first_name(self) -> str:
        """Get first name"""
        return self._first_name
    
    @first_name.setter
    def first_name(self, value: str) -> None:
        """Set first name with validation"""
        if not isinstance(value, str):
            raise TypeError("First name must be a string")
        if not value.strip():
            raise ValueError("First name cannot be empty")
        self._first_name = value.strip()
    
    @property
    def last_name(self) -> str:
        """Get last name"""
        return self._last_name
    
    @last_name.setter
    def last_name(self, value: str) -> None:
        """Set last name with validation"""
        if not isinstance(value, str):
            raise TypeError("Last name must be a string")
        if not value.strip():
            raise ValueError("Last name cannot be empty")
        self._last_name = value.strip()
    
    @property
    def full_name(self) -> str:
        """Get full name (computed property)"""
        return f"{self._first_name} {self._last_name}"
    
    @full_name.setter
    def full_name(self, value: str) -> None:
        """Set full name (splits into first and last)"""
        if not isinstance(value, str):
            raise TypeError("Full name must be a string")
        
        parts = value.strip().split()
        if len(parts) < 2:
            raise ValueError("Full name must contain at least first and last name")
        
        self._first_name = parts[0]
        self._last_name = " ".join(parts[1:])  # Handle multiple last names
    
    def __str__(self) -> str:
        return self.full_name
    
    def __repr__(self) -> str:
        return f"Person('{self._first_name}', '{self._last_name}')"

# Usage examples
person = Person("John", "Doe")
print(f"First name: {person.first_name}")
print(f"Last name: {person.last_name}")
print(f"Full name: {person.full_name}")

# Modify individual names
person.first_name = "Jane"
print(f"Updated full name: {person.full_name}")

# Set full name (splits automatically)
person.full_name = "Alice Johnson Smith"
print(f"First: {person.first_name}")
print(f"Last: {person.last_name}")
print(f"Full: {person.full_name}")

# Error handling
try:
    person.first_name = ""  # Raises ValueError
except ValueError as e:
    print(f"Error: {e}")
```

---

### 47. Speed Descriptor

**Question:** Create a descriptor for managing speed with validation.

**Answer:**

```python
class SpeedDescriptor:
    """Descriptor for managing speed with validation and conversion"""
    
    def __init__(self, min_speed=0, max_speed=300, unit="mph"):
        self.min_speed = min_speed
        self.max_speed = max_speed
        self.unit = unit
        self._name = None
    
    def __set_name__(self, owner, name):
        """Called when descriptor is assigned to class attribute"""
        self._name = name
        self._private_name = f'__{name}'
    
    def __get__(self, instance, owner):
        """Get the speed value"""
        if instance is None:
            return self
        return getattr(instance, self._private_name, 0)
    
    def __set__(self, instance, value):
        """Set the speed value with validation"""
        if not isinstance(value, (int, float)):
            raise TypeError(f"Speed must be a number, got {type(value).__name__}")
        
        if not (self.min_speed <= value <= self.max_speed):
            raise ValueError(
                f"Speed must be between {self.min_speed} and {self.max_speed} {self.unit}, "
                f"got {value}"
            )
        
        setattr(instance, self._private_name, float(value))
    
    def __delete__(self, instance):
        """Delete the speed value"""
        try:
            delattr(instance, self._private_name)
        except AttributeError:
            raise AttributeError(f"'{self._name}' not set")

class Vehicle:
    """Vehicle class using SpeedDescriptor"""
    speed = SpeedDescriptor(min_speed=0, max_speed=200, unit="mph")
    cruise_speed = SpeedDescriptor(min_speed=30, max_speed=150, unit="mph")
    
    def __init__(self, make: str, model: str):
        self.make = make
        self.model = model
        self.speed = 0  # Initialize speed
    
    def accelerate(self, amount: float):
        """Increase speed by amount"""
        self.speed += amount
    
    def brake(self, amount: float):
        """Decrease speed by amount"""
        self.speed = max(0, self.speed - amount)
    
    def __str__(self):
        return f"{self.make} {self.model} - Speed: {self.speed} mph"

# Advanced descriptor with logging
class LoggedSpeedDescriptor(SpeedDescriptor):
    """Speed descriptor with logging capabilities"""
    
    def __init__(self, *args, **kwargs):
        super().__init__(*args, **kwargs)
        self.history = []
    
    def __set__(self, instance, value):
        """Set speed and log the change"""
        old_value = getattr(instance, self._private_name, 0)
        super().__set__(instance, value)
        
        self.history.append({
            'timestamp': __import__('datetime').datetime.now(),
            'instance': id(instance),
            'old_value': old_value,
            'new_value': value
        })
    
    def get_history(self, instance=None):
        """Get speed change history"""
        if instance is None:
            return self.history
        return [h for h in self.history if h['instance'] == id(instance)]

class SportsCar:
    """Sports car with logged speed tracking"""
    speed = LoggedSpeedDescriptor(min_speed=0, max_speed=300, unit="mph")
    
    def __init__(self, make: str, model: str):
        self.make = make
        self.model = model

# Usage examples
car = Vehicle("Tesla", "Model S")
print(car)  # Tesla Model S - Speed: 0 mph

car.speed = 60
print(car)  # Tesla Model S - Speed: 60 mph

car.accelerate(20)
print(car)  # Tesla Model S - Speed: 80 mph

# Error handling
try:
    car.speed = 250  # Exceeds maximum
except ValueError as e:
    print(f"Error: {e}")

try:
    car.speed = "fast"  # Wrong type
except TypeError as e:
    print(f"Error: {e}")

# Sports car with logging
sports_car = SportsCar("Ferrari", "F40")
sports_car.speed = 100
sports_car.speed = 150
sports_car.speed = 120

print("Speed history:")
for entry in SportsCar.speed.get_history(sports_car):
    print(f"  {entry['timestamp'].strftime('%H:%M:%S')}: "
          f"{entry['old_value']} -> {entry['new_value']} mph")
```

---

## Concurrency & Performance

### 48. Generators vs. Iterators

**Question:** What's the difference between generators and iterators?

**Answer:**

```python
# Iterator implementation (class-based)
class SquareIterator:
    """Iterator that yields squares of numbers"""
    
    def __init__(self, max_value):
        self.max_value = max_value
        self.current = 0
    
    def __iter__(self):
        return self
    
    def __next__(self):
        if self.current >= self.max_value:
            raise StopIteration
        
        result = self.current ** 2
        self.current += 1
        return result

# Generator implementation (function-based)
def square_generator(max_value):
    """Generator that yields squares of numbers"""
    for i in range(max_value):
        yield i ** 2

# Advanced generator with state
def fibonacci_generator():
    """Infinite Fibonacci generator"""
    a, b = 0, 1
    while True:
        yield a
        a, b = b, a + b

# Generator expression (most concise)
squares_genexp = (i ** 2 for i in range(10))

# Comparison
print("Iterator approach:")
square_iter = SquareIterator(5)
for square in square_iter:
    print(square, end=" ")
print()

print("Generator approach:")
for square in square_generator(5):
    print(square, end=" ")
print()

print("Generator expression:")
for square in squares_genexp:
    print(square, end=" ")
print()

# Memory efficiency comparison
import sys

def memory_comparison():
    """Compare memory usage"""
    # List (stores all values)
    squares_list = [i ** 2 for i in range(1000)]
    
    # Generator (stores state only)
    squares_gen = (i ** 2 for i in range(1000))
    
    print(f"List memory usage: {sys.getsizeof(squares_list)} bytes")
    print(f"Generator memory usage: {sys.getsizeof(squares_gen)} bytes")

memory_comparison()

# Advanced: Generator with cleanup
class ManagedResourceGenerator:
    """Generator that manages resources"""
    
    def __init__(self, resource_name):
        self.resource_name = resource_name
    
    def __iter__(self):
        print(f"Acquiring resource: {self.resource_name}")
        try:
            for i in range(3):
                yield f"Data {i} from {self.resource_name}"
        finally:
            print(f"Releasing resource: {self.resource_name}")

# Usage
print("\nManaged resource generator:")
for data in ManagedResourceGenerator("Database"):
    print(f"  Processing: {data}")
```

---

### 49. Python Decorators

**Question:** Explain decorators and provide examples.

**Answer:**

```python
import time
import functools
from typing import Any, Callable

# Basic decorator
def timing_decorator(func: Callable) -> Callable:
    """Measure and print function execution time"""
    @functools.wraps(func)
    def wrapper(*args, **kwargs):
        start_time = time.time()
        result = func(*args, **kwargs)
        end_time = time.time()
        print(f"{func.__name__} executed in {end_time - start_time:.4f} seconds")
        return result
    return wrapper

# Decorator with arguments
def retry(max_attempts: int = 3, delay: float = 1):
    """Retry decorator with configurable attempts and delay"""
    def decorator(func: Callable) -> Callable:
        @functools.wraps(func)
        def wrapper(*args, **kwargs):
            last_exception = None
            
            for attempt in range(max_attempts):
                try:
                    return func(*args, **kwargs)
                except Exception as e:
                    last_exception = e
                    if attempt < max_attempts - 1:
                        print(f"Attempt {attempt + 1} failed: {e}. Retrying in {delay}s...")
                        time.sleep(delay)
                    else:
                        print(f"All {max_attempts} attempts failed.")
            
            raise last_exception
        return wrapper
    return decorator

# Class-based decorator
class CallCounter:
    """Count the number of times a function is called"""
    
    def __init__(self, func: Callable):
        self.func = func
        self.count = 0
        functools.update_wrapper(self, func)
    
    def __call__(self, *args, **kwargs):
        self.count += 1
        print(f"{self.func.__name__} has been called {self.count} times")
        return self.func(*args, **kwargs)

# Caching decorator (simplified version of functools.lru_cache)
def simple_cache(func: Callable) -> Callable:
    """Simple caching decorator"""
    cache = {}
    
    @functools.wraps(func)
    def wrapper(*args, **kwargs):
        # Create cache key from arguments
        key = str(args) + str(sorted(kwargs.items()))
        
        if key in cache:
            print(f"Cache hit for {func.__name__}")
            return cache[key]
        
        print(f"Computing {func.__name__}")
        result = func(*args, **kwargs)
        cache[key] = result
        return result
    
    return wrapper

# Usage examples
@timing_decorator
@simple_cache
def expensive_calculation(n: int) -> int:
    """Simulate expensive calculation"""
    time.sleep(0.1)  # Simulate work
    return sum(i ** 2 for i in range(n))

@retry(max_attempts=3, delay=0.5)
def unreliable_network_call():
    """Simulate unreliable network call"""
    import random
    if random.random() < 0.7:  # 70% chance of failure
        raise ConnectionError("Network timeout")
    return "Success!"

@CallCounter
def greet(name: str) -> str:
    return f"Hello, {name}!"

# Test the decorators
print("Testing expensive calculation:")
result1 = expensive_calculation(100)  # First call - computed
result2 = expensive_calculation(100)  # Second call - cached

print(f"\nResults: {result1}, {result2}")

print("\nTesting retry decorator:")
try:
    result = unreliable_network_call()
    print(f"Network call result: {result}")
except ConnectionError as e:
    print(f"Final error: {e}")

print("\nTesting call counter:")
greet("Alice")
greet("Bob")
greet("Charlie")

# Property decorator example
class Temperature:
    """Temperature class with validation"""
    
    def __init__(self, celsius: float = 0):
        self._celsius = celsius
    
    @property
    def celsius(self) -> float:
        return self._celsius
    
    @celsius.setter
    def celsius(self, value: float):
        if value < -273.15:
            raise ValueError("Temperature cannot be below absolute zero")
        self._celsius = value
    
    @property
    def fahrenheit(self) -> float:
        return (self._celsius * 9/5) + 32
    
    @fahrenheit.setter
    def fahrenheit(self, value: float):
        self.celsius = (value - 32) * 5/9

# Usage
temp = Temperature()
temp.celsius = 25
print(f"Temperature: {temp.celsius}°C = {temp.fahrenheit}°F")

temp.fahrenheit = 86
print(f"Temperature: {temp.celsius}°C = {temp.fahrenheit}°F")
```

---

## Data Structures & Algorithms

### 50. Performance Optimization

**Question:** How do you improve Python program performance?

**Answer:**

```python
import time
import cProfile
import timeit
from functools import lru_cache
from typing import List

# 1. Use appropriate data structures
def performance_data_structures():
    """Demonstrate impact of choosing right data structures"""
    
    # List vs Set for membership testing
    large_list = list(range(10000))
    large_set = set(range(10000))
    
    # Time list membership
    start = time.time()
    for _ in range(1000):
        5000 in large_list
    list_time = time.time() - start
    
    # Time set membership
    start = time.time()
    for _ in range(1000):
        5000 in large_set
    set_time = time.time() - start
    
    print(f"List membership: {list_time:.4f}s")
    print(f"Set membership: {set_time:.4f}s")
    print(f"Set is {list_time/set_time:.1f}x faster")

# 2. Use built-in functions and libraries
def sum_squares_slow(numbers: List[int]) -> int:
    """Slow implementation using loops"""
    total = 0
    for num in numbers:
        total += num * num
    return total

def sum_squares_fast(numbers: List[int]) -> int:
    """Fast implementation using built-ins"""
    return sum(num * num for num in numbers)

def sum_squares_numpy(numbers):
    """Fastest implementation using NumPy"""
    import numpy as np
    arr = np.array(numbers)
    return np.sum(arr * arr)

# 3. Use caching for expensive computations
@lru_cache(maxsize=None)
def fibonacci_cached(n: int) -> int:
    """Cached Fibonacci implementation"""
    if n < 2:
        return n
    return fibonacci_cached(n-1) + fibonacci_cached(n-2)

def fibonacci_uncached(n: int) -> int:
    """Uncached Fibonacci implementation"""
    if n < 2:
        return n
    return fibonacci_uncached(n-1) + fibonacci_uncached(n-2)

# 4. List comprehensions vs loops
def squares_loop(n: int) -> List[int]:
    """Create squares using loop"""
    result = []
    for i in range(n):
        result.append(i * i)
    return result

def squares_comprehension(n: int) -> List[int]:
    """Create squares using list comprehension"""
    return [i * i for i in range(n)]

# Performance testing
def run_performance_tests():
    """Run various performance tests"""
    numbers = list(range(1000))
    
    # Test data structure choice
    performance_data_structures()
    
    # Test different sum implementations
    print("\nSum of squares comparison:")
    slow_time = timeit.timeit(lambda: sum_squares_slow(numbers), number=1000)
    fast_time = timeit.timeit(lambda: sum_squares_fast(numbers), number=1000)
    
    print(f"Loop implementation: {slow_time:.4f}s")
    print(f"Built-in implementation: {fast_time:.4f}s")
    print(f"Built-in is {slow_time/fast_time:.1f}x faster")
    
    # Test caching
    print("\nFibonacci caching comparison:")
    n = 30
    
    cached_time = timeit.timeit(lambda: fibonacci_cached(n), number=1)
    uncached_time = timeit.timeit(lambda: fibonacci_uncached(n), number=1)
    
    print(f"Cached Fibonacci({n}): {cached_time:.4f}s")
    print(f"Uncached Fibonacci({n}): {uncached_time:.4f}s")
    print(f"Caching is {uncached_time/cached_time:.1f}x faster")

# 5. Profiling code
def profile_example():
    """Example of code profiling"""
    def slow_function():
        """Intentionally slow function"""
        result = 0
        for i in range(100000):
            result += i ** 2
        return result
    
    def fast_function():
        """Optimized version"""
        return sum(i ** 2 for i in range(100000))
    
    # Profile both functions
    print("\nProfiling slow function:")
    cProfile.run('slow_function()', globals={'slow_function': slow_function})
    
    print("\nProfiling fast function:")
    cProfile.run('fast_function()', globals={'fast_function': fast_function})

# run_performance_tests()
# profile_example()

# 6. Memory optimization techniques
class MemoryOptimizedClass:
    """Class using __slots__ to reduce memory usage"""
    __slots__ = ['x', 'y', 'z']
    
    def __init__(self, x, y, z):
        self.x = x
        self.y = y
        self.z = z

class RegularClass:
    """Regular class without __slots__"""
    
    def __init__(self, x, y, z):
        self.x = x
        self.y = y
        self.z = z

def memory_optimization_demo():
    """Demonstrate memory optimization with __slots__"""
    import sys
    
    # Create instances
    optimized = MemoryOptimizedClass(1, 2, 3)
    regular = RegularClass(1, 2, 3)
    
    print(f"Optimized class size: {sys.getsizeof(optimized)} bytes")
    print(f"Regular class size: {sys.getsizeof(regular)} bytes")
    
    # Create many instances
    optimized_instances = [MemoryOptimizedClass(i, i+1, i+2) for i in range(1000)]
    regular_instances = [RegularClass(i, i+1, i+2) for i in range(1000)]
    
    print(f"1000 optimized instances: {sum(sys.getsizeof(obj) for obj in optimized_instances)} bytes")
    print(f"1000 regular instances: {sum(sys.getsizeof(obj) for obj in regular_instances)} bytes")

memory_optimization_demo()
```

---

### 51. Serialization and Deserialization

**Question:** Explain serialization in Python with examples.

**Answer:**

```python
import pickle
import json
import csv
from datetime import datetime
from typing import Dict, List, Any
from dataclasses import dataclass, asdict

# 1. JSON Serialization (most common for web APIs)
def json_serialization_demo():
    """Demonstrate JSON serialization"""
    
    # Basic data types
    data = {
        'name': 'John Doe',
        'age': 30,
        'is_active': True,
        'scores': [85, 90, 78],
        'address': {
            'street': '123 Main St',
            'city': 'New York',
            'zip_code': '10001'
        }
    }
    
    # Serialize to JSON string
    json_string = json.dumps(data, indent=2)
    print("JSON serialized data:")
    print(json_string)
    
    # Deserialize from JSON string
    parsed_data = json.loads(json_string)
    print(f"Parsed data type: {type(parsed_data)}")
    print(f"Name: {parsed_data['name']}")
    
    # Save to file
    with open('data.json', 'w') as f:
        json.dump(data, f, indent=2)
    
    # Load from file
    with open('data.json', 'r') as f:
        loaded_data = json.load(f)
    
    return loaded_data

# Custom JSON encoder for datetime objects
class DateTimeEncoder(json.JSONEncoder):
    """Custom JSON encoder for datetime objects"""
    
    def default(self, obj):
        if isinstance(obj, datetime):
            return obj.isoformat()
        return super().default(obj)

def json_with_datetime():
    """JSON serialization with datetime objects"""
    data = {
        'timestamp': datetime.now(),
        'event': 'user_login',
        'user_id': 12345
    }
    
    # This would fail with default encoder
    # json_string = json.dumps(data)  # TypeError!
    
    # Use custom encoder
    json_string = json.dumps(data, cls=DateTimeEncoder, indent=2)
    print("JSON with datetime:")
    print(json_string)
    
    # Parse back (datetime becomes string)
    parsed = json.loads(json_string)
    print(f"Parsed timestamp type: {type(parsed['timestamp'])}")

# 2. Pickle Serialization (Python-specific)
@dataclass
class Person:
    """Example class for pickle serialization"""
    name: str
    age: int
    hobbies: List[str]
    
    def greet(self):
        return f"Hello, I'm {self.name}"

def pickle_serialization_demo():
    """Demonstrate pickle serialization"""
    
    # Create complex Python object
    person = Person("Alice", 30, ["reading", "hiking", "coding"])
    
    # Pickle to bytes
    pickled_data = pickle.dumps(person)
    print(f"Pickled data length: {len(pickled_data)} bytes")
    
    # Unpickle from bytes
    unpickled_person = pickle.loads(pickled_data)
    print(f"Unpickled person: {unpickled_person}")
    print(f"Can call methods: {unpickled_person.greet()}")
    
    # Save to file
    with open('person.pickle', 'wb') as f:
        pickle.dump(person, f)
    
    # Load from file
    with open('person.pickle', 'rb') as f:
        loaded_person = pickle.load(f)
    
    print(f"Loaded from file: {loaded_person}")
    
    # Pickle can handle complex nested structures
    complex_data = {
        'people': [person, Person("Bob", 25, ["gaming", "music"])],
        'metadata': {'created': datetime.now(), 'version': 1.0},
        'function': lambda x: x * 2  # Even functions!
    }
    
    pickled_complex = pickle.dumps(complex_data)
    unpickled_complex = pickle.loads(pickled_complex)
    
    print(f"Complex data preserved: {unpickled_complex['metadata']}")
    print(f"Function works: {unpickled_complex['function'](5)}")

# 3. CSV Serialization for tabular data
def csv_serialization_demo():
    """Demonstrate CSV serialization"""
    
    # Sample data
    people = [
        {'name': 'Alice', 'age': 30, 'city': 'New York'},
        {'name': 'Bob', 'age': 25, 'city': 'San Francisco'},
        {'name': 'Charlie', 'age': 35, 'city': 'Chicago'}
    ]
    
    # Write to CSV
    with open('people.csv', 'w', newline='') as csvfile:
        fieldnames = ['name', 'age', 'city']
        writer = csv.DictWriter(csvfile, fieldnames=fieldnames)
        
        writer.writeheader()
        for person in people:
            writer.writerow(person)
    
    # Read from CSV
    with open('people.csv', 'r') as csvfile:
        reader = csv.DictReader(csvfile)
        loaded_people = list(reader)
    
    print("Loaded from CSV:")
    for person in loaded_people:
        print(f"  {person}")

# 4. Custom serialization for specific use cases
class CustomSerializable:
    """Class with custom serialization logic"""
    
    def __init__(self, data: Dict[str, Any]):
        self.data = data
        self.created_at = datetime.now()
    
    def to_dict(self) -> Dict[str, Any]:
        """Convert to dictionary for serialization"""
        return {
            'data': self.data,
            'created_at': self.created_at.isoformat(),
            'class_name': self.__class__.__name__
        }
    
    @classmethod
    def from_dict(cls, data_dict: Dict[str, Any]) -> 'CustomSerializable':
        """Create instance from dictionary"""
        instance = cls(data_dict['data'])
        instance.created_at = datetime.fromisoformat(data_dict['created_at'])
        return instance
    
    def to_json(self) -> str:
        """Serialize to JSON string"""
        return json.dumps(self.to_dict(), indent=2)
    
    @classmethod
    def from_json(cls, json_string: str) -> 'CustomSerializable':
        """Deserialize from JSON string"""
        data_dict = json.loads(json_string)
        return cls.from_dict(data_dict)

def custom_serialization_demo():
    """Demonstrate custom serialization"""
    
    # Create object
    obj = CustomSerializable({'user_id': 123, 'action': 'login'})
    
    # Serialize to JSON
    json_data = obj.to_json()
    print("Custom serialized object:")
    print(json_data)
    
    # Deserialize from JSON
    restored_obj = CustomSerializable.from_json(json_data)
    print(f"Restored object data: {restored_obj.data}")
    print(f"Created at: {restored_obj.created_at}")

# Security warning about pickle
def pickle_security_warning():
    """Demonstrate pickle security concerns"""
    print("\nWARNING: Pickle Security Concerns")
    print("=" * 40)
    print("Never unpickle data from untrusted sources!")
    print("Pickle can execute arbitrary code during deserialization.")
    print("\nSafer alternatives for data exchange:")
    print("- JSON for web APIs")
    print("- CSV for tabular data")
    print("- XML for structured documents")
    print("- Protocol Buffers for high-performance systems")

# Run demonstrations
if __name__ == "__main__":
    json_serialization_demo()
    json_with_datetime()
    pickle_serialization_demo()
    csv_serialization_demo()
    custom_serialization_demo()
    pickle_security_warning()
```

---

### 52. Exception Handling

**Question:** Explain Python's exception handling mechanisms.

**Answer:**

```python
import logging
import traceback
from typing import Optional, Type
from contextlib import contextmanager

# 1. Basic exception handling
def basic_exception_handling():
    """Demonstrate basic try/except/else/finally"""
    
    def divide_numbers(a: float, b: float) -> Optional[float]:
        """Divide two numbers with error handling"""
        try:
            result = a / b
            print(f"Division successful: {a} / {b} = {result}")
            return result
        
        except ZeroDivisionError:
            print("Error: Cannot divide by zero!")
            return None
        
        except TypeError as e:
            print(f"Error: Invalid types for division - {e}")
            return None
        
        else:
            # Executes only if no exception occurred
            print("Division completed without errors")
        
        finally:
            # Always executes
            print("Division operation finished")
    
    # Test different scenarios
    print("Test 1: Valid division")
    divide_numbers(10, 2)
    
    print("\nTest 2: Division by zero")
    divide_numbers(10, 0)
    
    print("\nTest 3: Invalid types")
    divide_numbers(10, "abc")

# 2. Custom exceptions
class ValidationError(Exception):
    """Custom exception for validation errors"""
    
    def __init__(self, message: str, field: str = None):
        self.message = message
        self.field = field
        super().__init__(self.message)

class BusinessLogicError(Exception):
    """Custom exception for business logic errors"""
    pass

class User:
    """User class with validation"""
    
    def __init__(self, name: str, email: str, age: int):
        self.name = self._validate_name(name)
        self.email = self._validate_email(email)
        self.age = self._validate_age(age)
    
    def _validate_name(self, name: str) -> str:
        if not isinstance(name, str):
            raise ValidationError("Name must be a string", "name")
        if len(name.strip()) < 2:
            raise ValidationError("Name must be at least 2 characters", "name")
        return name.strip()
    
    def _validate_email(self, email: str) -> str:
        if not isinstance(email, str):
            raise ValidationError("Email must be a string", "email")
        if "@" not in email or "." not in email:
            raise ValidationError("Email must be valid format", "email")
        return email.lower()
    
    def _validate_age(self, age: int) -> int:
        if not isinstance(age, int):
            raise ValidationError("Age must be an integer", "age")
        if age < 0 or age > 150:
            raise ValidationError("Age must be between 0 and 150", "age")
        return age

def custom_exception_demo():
    """Demonstrate custom exceptions"""
    
    def create_user(name: str, email: str, age: int) -> Optional[User]:
        """Create user with comprehensive error handling"""
        try:
            user = User(name, email, age)
            print(f"User created successfully: {user.name}")
            return user
        
        except ValidationError as e:
            print(f"Validation Error in field '{e.field}': {e.message}")
            return None
        
        except Exception as e:
            print(f"Unexpected error: {e}")
            return None
    
    # Test valid user
    create_user("John Doe", "john@example.com", 30)
    
    # Test invalid users
    create_user("", "john@example.com", 30)  # Invalid name
    create_user("John", "invalid-email", 30)  # Invalid email
    create_user("John", "john@example.com", -5)  # Invalid age

# 3. Exception chaining and context
def exception_chaining_demo():
    """Demonstrate exception chaining"""
    
    def process_data(data):
        """Process data with chained exceptions"""
        try:
            # Simulate data processing
            if not data:
                raise ValueError("Data cannot be empty")
            
            # Simulate conversion error
            result = int(data)
            return result * 2
        
        except ValueError as e:
            # Chain the exception with additional context
            raise BusinessLogicError("Failed to process user data") from e
    
    def handle_user_request(user_input):
        """Handle user request with proper error context"""
        try:
            result = process_data(user_input)
            print(f"Processing successful: {result}")
        
        except BusinessLogicError as e:
            print(f"Business Logic Error: {e}")
            print(f"Original cause: {e.__cause__}")
            
            # Print full traceback for debugging
            print("\nFull traceback:")
            traceback.print_exc()
    
    # Test with invalid data
    handle_user_request("invalid")

# 4. Context managers for exception handling
@contextmanager
def database_transaction():
    """Simulate database transaction context manager"""
    print("Starting database transaction...")
    transaction_active = True
    
    try:
        yield
        print("Committing transaction...")
    
    except Exception as e:
        print(f"Rolling back transaction due to error: {e}")
        raise
    
    finally:
        if transaction_active:
            print("Closing database connection...")

def context_manager_exception_demo():
    """Demonstrate exception handling with context managers"""
    
    def safe_database_operation():
        """Safe database operation"""
        with database_transaction():
            print("Performing database operations...")
            # Simulate successful operations
            return "Data saved successfully"
    
    def unsafe_database_operation():
        """Unsafe database operation that fails"""
        with database_transaction():
            print("Performing database operations...")
            raise RuntimeError("Database connection failed")
    
    # Test successful operation
    print("=== Successful Operation ===")
    try:
        result = safe_database_operation()
        print(f"Result: {result}")
    except Exception as e:
        print(f"Operation failed: {e}")
    
    # Test failed operation
    print("\n=== Failed Operation ===")
    try:
        unsafe_database_operation()
    except Exception as e:
        print(f"Operation failed: {e}")

# 5. Logging exceptions
def setup_logging():
    """Setup logging configuration"""
    logging.basicConfig(
        level=logging.INFO,
        format='%(asctime)s - %(levelname)s - %(message)s',
        handlers=[
            logging.FileHandler('app.log'),
            logging.StreamHandler()
        ]
    )

def logging_exceptions_demo():
    """Demonstrate exception logging"""
    setup_logging()
    logger = logging.getLogger(__name__)
    
    def risky_operation(value):
        """Operation that might fail"""
        try:
            if value < 0:
                raise ValueError(f"Negative value not allowed: {value}")
            
            result = 100 / value
            logger.info(f"Operation successful: 100 / {value} = {result}")
            return result
        
        except ValueError as e:
            logger.error(f"Value error in risky_operation: {e}")
            raise
        
        except ZeroDivisionError as e:
            logger.critical(f"Division by zero in risky_operation: {e}")
            raise
        
        except Exception as e:
            logger.exception(f"Unexpected error in risky_operation: {e}")
            raise
    
    # Test different scenarios
    try:
        risky_operation(5)    # Success
        risky_operation(0)    # Division by zero
    except Exception:
        pass
    
    try:
        risky_operation(-1)   # Negative value
    except Exception:
        pass

# 6. Exception handling best practices
class ExceptionHandlingBestPractices:
    """Demonstrate exception handling best practices"""
    
    @staticmethod
    def be_specific_with_exceptions():
        """Use specific exception types"""
        
        # BAD: Catching all exceptions
        def bad_exception_handling():
            try:
                result = int("abc")
            except:  # Too broad!
                print("Something went wrong")
        
        # GOOD: Catching specific exceptions
        def good_exception_handling():
            try:
                result = int("abc")
            except ValueError as e:
                print(f"Invalid integer conversion: {e}")
            except TypeError as e:
                print(f"Type error: {e}")
    
    @staticmethod
    def dont_suppress_exceptions():
        """Don't suppress exceptions without good reason"""
        
        # BAD: Silently ignoring exceptions
        def bad_suppression():
            try:
                risky_operation()
            except Exception:
                pass  # Silent failure!
        
        # GOOD: Handle or re-raise exceptions
        def good_handling():
            try:
                risky_operation()
            except SpecificException as e:
                logger.error(f"Expected error occurred: {e}")
                # Handle the error appropriately
            except Exception as e:
                logger.critical(f"Unexpected error: {e}")
                raise  # Re-raise unexpected exceptions
    
    @staticmethod
    def use_finally_for_cleanup():
        """Use finally blocks for cleanup"""
        
        def resource_management():
            resource = None
            try:
                resource = acquire_resource()
                process_with_resource(resource)
            except ResourceError as e:
                print(f"Resource error: {e}")
            finally:
                if resource:
                    release_resource(resource)

# Run all demonstrations
if __name__ == "__main__":
    print("=== Basic Exception Handling ===")
    basic_exception_handling()
    
    print("\n=== Custom Exceptions ===")
    custom_exception_demo()
    
    print("\n=== Exception Chaining ===")
    exception_chaining_demo()
    
    print("\n=== Context Manager Exceptions ===")
    context_manager_exception_demo()
    
    print("\n=== Exception Logging ===")
    logging_exceptions_demo()
```

---

### 53. Virtual Environments

**Question:** Explain virtual environments and their importance.

**Answer:**

```python
import os
import sys
import subprocess
from pathlib import Path

def virtual_environment_explanation():
    """
    Virtual environments are isolated Python installations that allow
    different projects to have their own dependencies without conflicts.
    """
    
    print("Virtual Environment Benefits:")
    print("=" * 40)
    print("1. Dependency Isolation - Each project has its own packages")
    print("2. Version Management - Different projects can use different package versions")  
    print("3. Clean System - Keeps global Python installation clean")
    print("4. Reproducibility - Easy to recreate environments")
    print("5. Testing - Test with different Python/package versions")
    
    print("\nCurrent Environment Info:")
    print(f"Python executable: {sys.executable}")
    print(f"Python version: {sys.version}")
    print(f"Python path: {sys.path[:3]}...")  # Show first 3 paths
    
    # Check if in virtual environment
    if hasattr(sys, 'real_prefix') or (hasattr(sys, 'base_prefix') and sys.base_prefix != sys.prefix):
        print("✅ Currently in a virtual environment")
        print(f"Virtual env path: {sys.prefix}")
    else:
        print("❌ Not in a virtual environment (using system Python)")

def demonstrate_venv_commands():
    """Show common virtual environment commands"""
    
    commands = {
        "Create virtual environment": [
            "python -m venv myproject_env",
            "python3 -m venv myproject_env",  # On systems with both Python 2 & 3
        ],
        
        "Activate virtual environment": [
            "# Windows:",
            "myproject_env\\Scripts\\activate",
            "",
            "# macOS/Linux:",
            "source myproject_env/bin/activate",
        ],
        
        "Install packages": [
            "pip install requests",
            "pip install django==4.2.0",  # Specific version
            "pip install -r requirements.txt",  # From file
        ],
        
        "Manage packages": [
            "pip list",  # Show installed packages
            "pip freeze",  # Show packages with versions
            "pip freeze > requirements.txt",  # Save current packages
            "pip show requests",  # Show package info
            "pip uninstall requests",  # Remove package
        ],
        
        "Deactivate virtual environment": [
            "deactivate",
        ],
        
        "Remove virtual environment": [
            "# Simply delete the directory:",
            "rm -rf myproject_env  # macOS/Linux",
            "rmdir /s myproject_env  # Windows",
        ]
    }
    
    print("Common Virtual Environment Commands:")
    print("=" * 50)
    
    for category, command_list in commands.items():
        print(f"\n{category}:")
        for cmd in command_list:
            if cmd.startswith("#"):
                print(f"  {cmd}")  # Comment
            elif cmd == "":
                print()  # Empty line
            else:
                print(f"  $ {cmd}")

def project_structure_example():
    """Show recommended project structure with virtual environment"""
    
    structure = """
    my_project/
    ├── myproject_env/          # Virtual environment (add to .gitignore)
    │   ├── bin/               # Executables (Linux/macOS)
    │   ├── Scripts/           # Executables (Windows)
    │   ├── lib/               # Installed packages
    │   └── pyvenv.cfg         # Environment configuration
    ├── src/                   # Source code
    │   ├── __init__.py
    │   ├── main.py
    │   └── utils.py
    ├── tests/                 # Test files
    │   ├── test_main.py
    │   └── test_utils.py
    ├── requirements.txt       # Package dependencies
    ├── requirements-dev.txt   # Development dependencies
    ├── .gitignore            # Exclude venv and other files
    ├── README.md             # Project documentation
    └── setup.py              # Package configuration
    """
    
    print("Recommended Project Structure:")
    print("=" * 40)
    print(structure)

def requirements_file_example():
    """Show examples of requirements.txt files"""
    
    basic_requirements = """
# Basic requirements.txt example
requests>=2.28.0
flask==2.3.0
pandas>=1.5.0,<2.0.0
numpy
python-dotenv==1.0.0
"""
    
    dev_requirements = """
# requirements-dev.txt example (development dependencies)
-r requirements.txt  # Include base requirements
pytest>=7.0.0
black==23.0.0
flake8==6.0.0
mypy>=1.0.0
jupyter>=1.0.0
pre-commit>=3.0.0
"""
    
    print("Requirements.txt Examples:")
    print("=" * 30)
    
    print("requirements.txt:")
    print(basic_requirements)
    
    print("requirements-dev.txt:")
    print(dev_requirements)
    
    print("Version Specifiers:")
    print("  ==  Exactly equal to version")
    print("  >=  Greater than or equal to version")
    print("  <=  Less than or equal to version")
    print("  >   Greater than version")
    print("  <   Less than version")
    print("  !=  Not equal to version")
    print("  ~=  Compatible release (e.g., ~=1.4 means >=1.4.0, <1.5.0)")

def conda_vs_venv():
    """Compare conda and venv"""
    
    comparison = {
        "Feature": ["Package Manager", "Environment Manager", "Language Support", 
                   "Binary Dependencies", "Scientific Libraries", "Performance"],
        "venv + pip": ["pip", "venv", "Python only", "Limited", "Good", "Fast"],
        "conda": ["conda", "conda", "Multi-language", "Excellent", "Excellent", "Can be slower"]
    }
    
    print("Conda vs venv + pip Comparison:")
    print("=" * 40)
    
    # Simple table format
    for i, feature in enumerate(comparison["Feature"]):
        venv_val = comparison["venv + pip"][i]
        conda_val = comparison["conda"][i]
        print(f"{feature:20} | {venv_val:15} | {conda_val}")
    
    print("\nWhen to use what:")
    print("Use venv + pip when:")
    print("  - Working with pure Python projects")
    print("  - Want lightweight solution")
    print("  - Following Python standard practices")
    
    print("\nUse conda when:")
    print("  - Working with data science/scientific computing")
    print("  - Need complex binary dependencies")
    print("  - Managing multiple languages (Python + R + Julia)")
    print("  - Need different Python versions per project")

def best_practices():
    """Virtual environment best practices"""
    
    practices = [
        "Always use virtual environments for projects",
        "Add virtual environment folder to .gitignore",
        "Use descriptive names for environments",
        "Keep requirements.txt up to date",
        "Use separate requirements files for dev/prod",
        "Pin important package versions",
        "Regularly update dependencies (with testing)",
        "Document environment setup in README",
        "Use tools like pipenv or poetry for advanced workflows",
        "Consider using pyenv for Python version management"
    ]
    
    print("Virtual Environment Best Practices:")
    print("=" * 40)
    
    for i, practice in enumerate(practices, 1):
        print(f"{i:2d}. {practice}")

def automation_example():
    """Show automation scripts for virtual environments"""
    
    setup_script = '''#!/bin/bash
# setup.sh - Automated environment setup script

echo "Setting up Python virtual environment..."

# Create virtual environment
python3 -m venv venv

# Activate virtual environment
source venv/bin/activate

# Upgrade pip
pip install --upgrade pip

# Install dependencies
if [ -f requirements.txt ]; then
    pip install -r requirements
