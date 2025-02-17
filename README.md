# Week 1: Python Basics

## Installing Python & Using an IDE

1. **Download Python** from [python.org](https://www.python.org/downloads/). This is necessary to run Python programs on your computer. Python is an interpreted language, so it needs to be installed for you to execute code.
   
2. **Choose an IDE**:
   - **VS Code**: A lightweight, extensible editor.
   - **PyCharm**: A full-fledged IDE with advanced features for Python.
   - **Jupyter Notebook**: Ideal for data science tasks and interactive code execution.

3. **Verify Installation**: 
   Open the terminal and type `python --version` to check if Python is properly installed. It should display something like `Python 3.x.x`.

4. **Run Python**:
   - Open the terminal or use the IDE. Type `python` to enter the Python interactive shell or create a file with a `.py` extension (e.g., `hello.py`) and run it by typing `python hello.py` in the terminal.

---

## Variables and Data Types

In Python, variables store values of different types. Here are examples:

- **Integers** are whole numbers (e.g., `10`).
- **Floats** are decimal numbers (e.g., `3.14`).
- **Strings** are sequences of characters (e.g., `"Alice"`).
- **Booleans** represent truth values, `True` or `False`.

**Checking types**:

```python   
x = 10  # Integer
y = 3.14  # Float
name = "Alice"  # String
is_active = True  # Boolean

print(type(x), type(y), type(name), type(is_active))
```

This will print the data types of each variable.

---

## Basic Input/Output

- **`input()`**: This function allows users to enter data.
- **`print()`**: This function displays output.

Example:
```python
name = input("Enter your name: ")
print("Hello, " + name + "!")
```

1. It prompts the user to enter their name.
2. It then prints a greeting using that name.

---

## Operators

Operators perform operations on variables. Common operators:
- **Arithmetic**: `+`, `-`, `*`, `/`, `%`, `//`, `**`
   - `+` adds, `-` subtracts, `*` multiplies, `/` divides, `%` calculates remainder, `//` is floor division, and `**` is exponentiation.

Example:
```python
a, b = 10, 3
print(a + b, a - b, a * b, a / b, a % b, a // b, a ** b)
```

This will print the results of all the arithmetic operations between `a` and `b`.

---

## Conditional Statements

These control the flow of the program by making decisions.

Example:
```python
num = int(input("Enter a number: "))
if num % 2 == 0:
    print("Even")
else:
    print("Odd")
```

- **`if`** checks if the number is even by using modulo operation `%`.
- If the condition is `True`, it prints `"Even"`, otherwise `"Odd"`.

---

## Loops

Loops allow repeating code multiple times.

1. **`for` loop**: Iterates over a range or a collection.
```python
for i in range(1, 11):
    print(i)
```

This prints numbers 1 through 10.

2. **`while` loop**: Repeats as long as a condition is `True`.
```python
i = 1
while i <= 10:
    print(i)
    i += 1
```

This also prints numbers 1 through 10 using a `while` loop.

---

# Week 2: Functions and File Handling

## Defining Functions

Functions are reusable blocks of code that perform a specific task.

Example:
```python
def greet(name):
    return f"Hello, {name}!"
```

- **`def`** creates a function called `greet`.
- It takes one argument `name` and returns a greeting message.
- **Calling the function**: `print(greet("Alice"))` will print `"Hello, Alice!"`.

---

## File Handling

Python provides ways to interact with files.

- **Write to a file**:
```python
with open("sample.txt", "w") as file:
    file.write("Hello, world!")
```

- This opens (or creates) a file named `sample.txt` in write mode (`"w"`) and writes `"Hello, world!"`.

- **Read from a file**:
```python
with open("sample.txt", "r") as file:
    print(file.read())
```

- This opens the file in read mode (`"r"`) and prints the content.

---

## String Manipulation

You can manipulate strings using built-in methods.

```python
text = "Hello, world!"
words = text.split()  # Splits string by spaces into a list
print(words)  # ['Hello,', 'world!']

# Join words back into a string
print(" ".join(words))  # 'Hello, world!'
```

- **`split()`**: Breaks a string into a list based on spaces (or other delimiters).
- **`join()`**: Joins elements of a list into a single string with spaces.

---

# Week 3: Lists, Dictionaries, and OOP

## Lists

Lists store multiple values in an ordered collection.
```python
students = ["Alice", "Bob", "Charlie"]
students.append("David")  # Adds 'David' to the list
print(students)  # ['Alice', 'Bob', 'Charlie', 'David']
```

---

## Dictionaries

Dictionaries store data in key-value pairs.
```python
student = {"name": "Alice", "age": 20, "grade": "A"}
print(student["name"])  # Alice
```

---

## Object-Oriented Programming (OOP)

OOP organizes code using **classes** and **objects**.

1. **Classes & Objects**:
```python
class Student:
    def __init__(self, name, age, grade):
        self.name = name
        self.age = age
        self.grade = grade

s1 = Student("Alice", 20, "A")
print(s1.name)  # Alice
```

- **`__init__`** is a special method called the constructor. It initializes the object’s attributes when a new instance is created.

2. **Methods**:
```python
class Student:
    def __init__(self, name, age, grade):
        self.name = name
        self.age = age
        self.grade = grade
    
    def get_info(self):
        return f"{self.name}, Age: {self.age}, Grade: {self.grade}"

s1 = Student("Alice", 20, "A")
print(s1.get_info())  # Alice, Age: 20, Grade: A
```

3. **Encapsulation**:
```python
class Student:
    def __init__(self, name, age):
        self.__name = name  # Private attribute
        self.__age = age
    
    def get_name(self):
        return self.__name
    
    def set_name(self, new_name):
        self.__name = new_name
```

- **Private attributes** (e.g., `self.__name`) are hidden, and can only be accessed via **getter** and **setter** methods.

---

### Inheritance & Polymorphism

Inheritance allows a class to inherit methods and properties from another class.
```python
class Person:
    def __init__(self, name):
        self.name = name
    
    def speak(self):
        return "Hello!"

class Student(Person):
    def __init__(self, name, grade):
        super().__init__(name)
        self.grade = grade
    
    def speak(self):
        return f"I am a student named {self.name} and I am in grade {self.grade}."

s = Student("Alice", "10th")
print(s.speak())  # I am a student named Alice and I am in grade 10th.
```

- **`super().__init__()`** calls the constructor of the parent class (`Person`).

---

# Week 4: Data Structures & Algorithm Basics

## Stacks & Queues

- **Stack**: Last In, First Out (LIFO).
```python
stack = []
stack.append(1)
stack.append(2)
print(stack.pop())  # 2
```

- **Queue**: First In, First Out (FIFO).
```python
from collections import deque
queue = deque([1, 2, 3])
queue.append(4)
print(queue.popleft())  # 1
```

---

## Sorting Algorithms: Insertion Sort

Insertion sort sorts an array by repeatedly inserting the current element into its correct position.

```python
def insertion_sort(arr):
    for i in range(1, len(arr)):
        key = arr[i]
        j = i - 1
        while j >= 0 and key < arr[j]:
            arr[j + 1] = arr[j]
            j -= 1
        arr[j + 1] = key
    return arr
```

- This algorithm shifts elements until the correct spot for the `key` element is found.

---

## Searching Algorithms

1. **Linear Search**:
```python
def linear_search(arr, target):
    for i in range(len(arr)):
        if arr[i] == target:
            return i
    return -1
```

2. **Binary Search** (requires sorted array):
```python
def binary_search(arr, target):
    left, right = 0, len(arr) - 1
    while left <= right:
        mid = (left + right) // 2
        if arr[mid] == target:
            return mid
        elif arr[mid] < target:
            left = mid + 1
        else:
            right = mid - 1
    return -1
```

---

# Final Tips

- **Practice daily**: Coding requires consistent practice.
- **Debugging**: When errors occur, take time to understand them.
- **Python Docs**: Reference official documentation to deepen your understanding ([docs.python.org](https://docs.python.org/3/)).
```

</rewritten_file>
