# Python Tutrial
Python is a high-level, interpreted, and general-purpose programming language that emphasizes simplicity, readability, and ease of use. Developed by Guido van Rossum and first released in 1991, Python has since become one of the most popular programming languages worldwide, renowned for its versatility and vast ecosystem of libraries and frameworks.

Key features of Python include:

1. **Readable and expressive syntax**: Python's syntax is designed to be clear and readable, resembling natural language, which makes it accessible to beginners and enjoyable for experienced programmers.

2. **Interpreted**: Python code is executed line by line by an interpreter, which means there is no need for compilation before running the code. This facilitates rapid development and experimentation.

3. **Dynamic typing**: Python is dynamically typed, meaning you don't need to specify the data type of a variable explicitly. Variable types are inferred at runtime, allowing for flexible and concise code.

4. **Strongly typed**: Despite being dynamically typed, Python is strongly typed, which means it enforces strict type-checking rules to prevent unintended errors and ensure code reliability.

5. **Rich standard library**: Python comes with a comprehensive standard library that provides support for various tasks, including file I/O, networking, web development, data processing, and more, reducing the need for external dependencies.

6. **Extensive ecosystem**: Python has a vast ecosystem of third-party libraries and frameworks for almost every imaginable task, ranging from scientific computing (NumPy, SciPy) and machine learning (TensorFlow, PyTorch) to web development (Django, Flask) and data analysis (Pandas).

7. **Cross-platform**: Python is available on multiple platforms, including Windows, macOS, and Linux, making it highly portable and versatile for developing applications across different environments.

8. **Community-driven**: Python has a large and active community of developers who contribute to its development, provide support, share knowledge, and create a wealth of resources, tutorials, and tools.

Python is widely used in various domains, including web development, data science, artificial intelligence, machine learning, scientific computing, automation, scripting, and more. Its simplicity, flexibility, and robustness make it an ideal choice for both beginners and experienced programmers alike.

## Comments
Comments in programming code are non-executable statements used to provide explanations, documentation, or annotations within the code itself. They are ignored by the compiler or interpreter and do not affect the execution of the program. Comments are essential for improving code readability, understanding, and maintenance. Here are some key points about comments:

1. **Purpose**: Comments are used to clarify the purpose of certain code sections, describe algorithms, provide context, or document important information such as variable meanings, function behavior, and program structure.

2. **Types**: Comments can be single-line or multi-line. Single-line comments typically start with a designated symbol (e.g., `#` in Python, `//` in C, C++, Java) and continue until the end of the line. Multi-line comments can span across multiple lines and are enclosed within specific delimiters (e.g., `/* */` in C, C++, Java).

3. **Documentation**: Comments are commonly used for documenting code, especially in the form of docstrings in languages like Python. Docstrings provide structured documentation for functions, classes, and modules, making them accessible via tools like automated documentation generators.

4. **Debugging**: Comments can also be used for debugging purposes by temporarily disabling code segments or adding notes about debugging steps, known issues, or future improvements.

5. **Best Practices**: Writing clear, concise, and meaningful comments is essential for effective communication and collaboration among developers. It's important to maintain comments alongside the code, keeping them up-to-date with any changes made to the codebase.

6. **Avoid Overcommenting**: While comments are valuable for enhancing code readability, it's essential to strike a balance and avoid excessive or redundant comments. Code should ideally be self-explanatory, with comments used to supplement understanding where necessary.

Here's an example of comments in Python code:

```python
# This is a single-line comment

"""
This is a multi-line comment.
It spans multiple lines and is enclosed within triple quotes.
"""

# Function to calculate the factorial of a number
def factorial(n):
    if n == 0:
        return 1  # Returning 1 for the factorial of 0
    else:
        return n * factorial(n-1)
```

In this example, comments are used to describe the purpose of the code, provide function documentation, and clarify specific parts of the implementation.

Sure! Here are various examples of comments in Python 3:

1. Single-line comment:
```python
# This is a single-line comment
```

2. Multi-line comment using triple quotes:
```python
"""
This is a multi-line comment.
It spans multiple lines and is enclosed within triple quotes.
"""
```

3. Commenting out code:
```python
# This line is commented out
# print("This line is commented out and won't be executed")
```

4. Commenting to explain code logic:
```python
# Calculate the sum of two numbers
x = 5
y = 10
# Add x and y
sum = x + y
```

5. Commenting function definitions:
```python
# Function to calculate the factorial of a number
def factorial(n):
    if n == 0:
        return 1  # Factorial of 0 is defined as 1
    else:
        return n * factorial(n-1)
```

6. Commenting class definitions:
```python
# Class representing a car
class Car:
    def __init__(self, make, model):
        self.make = make
        self.model = model
    # Method to start the car
    def start(self):
        print("The car is starting.")
```

7. Docstring for documenting functions:
```python
def greet(name):
    """
    This function greets the person with the given name.

    Parameters:
    name (str): The name of the person to greet.
    """
    print("Hello,", name)
```

8. Commenting to provide context or explanation:
```python
# Loop through the list of names and print each one
names = ["Alice", "Bob", "Charlie"]
for name in names:
    print(name)
```

These examples demonstrate various ways to use comments in Python code to improve readability, document code functionality, and provide explanations or context for better understanding.

## Docstring

In Python, a docstring is a string literal that occurs as the first statement in a module, function, class, or method definition. Docstrings are used to document code by providing a concise description of what the code does, how to use it, and any other relevant information. Docstrings are not just regular comments; they serve a specific purpose and can be accessed programmatically.

Here are some key points about docstrings in Python:

1. **Purpose**: Docstrings serve as documentation for Python modules, functions, classes, and methods. They help users and developers understand the purpose, usage, and behavior of the code without needing to read through the implementation details.

2. **Location**: Docstrings are placed immediately after the header (the first line) of a module, function, class, or method definition. They are enclosed within triple quotes (`""" """`) for multi-line strings or single quotes (`''' '''` or `''' '''`) for single-line strings.

3. **Access**: Docstrings can be accessed programmatically using the `__doc__` attribute of the module, function, class, or method. This allows tools like help(), dir(), and documentation generators to retrieve and display the documentation string.

4. **Format**: There are different conventions for writing docstrings in Python, such as Google-style docstrings, reStructuredText (reST) docstrings, and NumPy docstrings. These conventions provide guidelines on how to structure and format docstrings to ensure consistency and readability across codebases.

5. **Content**: A well-written docstring typically includes a brief description of what the code does, any parameters or arguments it accepts (for functions and methods), return values (if applicable), exceptions raised, usage examples, and any other relevant information.

6. **Documentation Tools**: Python's standard library includes tools like pydoc and the `help()` function, which can display docstrings interactively. Additionally, there are third-party documentation generators like Sphinx that can generate HTML, PDF, and other documentation formats from docstrings.

Here's an example of a function with a docstring:

```python
def add(a, b):
    """
    This function calculates the sum of two numbers.

    Parameters:
    a (int): The first number.
    b (int): The second number.

    Returns:
    int: The sum of a and b.
    """
    return a + b
```

In this example, the docstring provides a description of what the `add()` function does, specifies the parameters it accepts (`a` and `b`), and describes the return value.

Certainly! Here are various examples of docstrings in Python 3:

1. Docstring for a function:
```python
def greet(name):
    """
    This function greets the person with the given name.

    Parameters:
    name (str): The name of the person to greet.

    Returns:
    str: A greeting message addressed to the person.
    """
    return f"Hello, {name}!"
```

2. Docstring for a class:
```python
class Dog:
    """
    A class representing a dog.

    Attributes:
    name (str): The name of the dog.
    age (int): The age of the dog in years.
    breed (str): The breed of the dog.
    """

    def __init__(self, name, age, breed):
        self.name = name
        self.age = age
        self.breed = breed

    def bark(self):
        """Make the dog bark."""
        return "Woof! Woof!"
```

3. Docstring for a module:
```python
"""
This module contains utility functions for working with strings.
"""

def count_vowels(text):
    """
    Count the number of vowels in a given text.

    Parameters:
    text (str): The input text.

    Returns:
    int: The number of vowels in the text.
    """
    vowels = "aeiouAEIOU"
    return sum(1 for char in text if char in vowels)
```

4. Docstring for a method within a class:
```python
class Circle:
    """
    A class representing a circle.

    Attributes:
    radius (float): The radius of the circle.
    """

    def __init__(self, radius):
        self.radius = radius

    def area(self):
        """
        Calculate the area of the circle.

        Returns:
        float: The area of the circle.
        """
        return 3.14 * self.radius ** 2
```

These examples demonstrate different ways of using docstrings to document modules, functions, classes, and methods in Python 3. Docstrings provide valuable information about the purpose, usage, and behavior of the code, making it easier for users and developers to understand and utilize the code effectively.


## Printing

Examples of `print` statements in Python 3:

1. Printing a string:

You can print a string by either single quote or double quote

```python
print("Hello, world!")
print('Hello, world!')
```

1. Printing variables:
```python
name = "Alice"
age = 30
print("Name:", name, "Age:", age)
```

1. Printing with formatted strings (f-strings):
```python
name = "Bob"
age = 25
print(f"Name: {name}, Age: {age}")
```

1. Printing with format method:
```python
name = "Charlie"
age = 40
print("Name: {}, Age: {}".format(name, age))
```

1. Printing with multiple arguments:
```python
x = 5
y = 10
print("x =", x, ", y =", y)
```

1. Printing with custom separators:
```python
print("a", "b", "c", sep="-")
# Output: a-b-c
```

1. Printing to a file:
```python
with open("output.txt", "w") as f:
    print("This is written to a file", file=f)
```

1. Printing without newline (using `end` parameter):
```python
print("Hello", end=" ")
print("World")
# Output: Hello World (without a newline in between)
```

## variables

In programming languages, variables are used to store data that can be referenced and manipulated throughout the program. Variables provide a way to label and store information temporarily in computer memory. Here are some key points about variables in programming languages:

1. **Storage Location**: Variables allocate memory space to hold data. This space can vary depending on the type and size of the data being stored.

2. **Data Types**: Variables have data types that define the type of data they can hold, such as integers, floating-point numbers, strings, boolean values, etc. The data type determines the operations that can be performed on the variable and the amount of memory it occupies.

3. **Name**: Each variable has a unique name that is used to refer to it in the program. Variable names must adhere to certain rules depending on the programming language, such as starting with a letter or underscore, and can include letters, digits, and underscores.

4. **Value**: Variables hold values that can be assigned and changed during the execution of the program. These values can be literals (explicitly written values) or the result of expressions.

5. **Scope**: Variables have a scope, which defines where in the program they can be accessed. Variables can have local scope (limited to a specific block or function) or global scope (accessible throughout the entire program).

6. **Mutability**: Depending on the programming language, variables may be mutable or immutable. Mutable variables allow their values to be changed after they are created, while immutable variables cannot be modified once they are assigned a value.

7. **Declaration and Initialization**: In statically-typed languages, variables often need to be declared with their data type before they can be used. In dynamically-typed languages, variables can be used without explicit declaration, and their type is inferred from the value assigned to them. Initialization refers to the process of assigning an initial value to a variable.

Overall, variables are fundamental building blocks in programming languages, enabling developers to work with and manipulate data in their programs effectively.

These examples demonstrate the versatility of variables in Python, allowing you to store different types of data and manipulate them as needed in your code.

Sure, here's a table listing Python 3 variable types along with their names and descriptions:

| Variable Type   | Name           | Description                                                                       |
|-----------------|----------------|-----------------------------------------------------------------------------------|
| Integer         | int            | Whole numbers without fractional parts.                                           |
| Float           | float          | Numbers with fractional parts.                                                     |
| String          | str            | Sequence of characters, enclosed in single quotes ('') or double quotes ("").     |
| Boolean         | bool           | Represents True or False values.                                                   |
| List            | list           | Ordered collection of items, mutable (modifiable).                                 |
| Tuple           | tuple          | Ordered collection of items, immutable (unchangeable).                             |
| Dictionary      | dict           | Collection of key-value pairs, unordered and mutable.                              |
| Set             | set            | Unordered collection of unique elements, mutable.                                  |
| NoneType        | None           | Represents absence of a value or a null value.                                     |
| Complex         | complex        | Numbers with a real and imaginary part.                                            |
| Bytes           | bytes          | Immutable sequence of bytes.                                                       |
| Bytearray       | bytearray      | Mutable sequence of bytes.                                                         |

These are the built-in variable types available in Python 3. Each serves a different purpose and can be used in various ways within your programs.

1. Integer Variable:
```python
age = 25
```

2. Float Variable:
```python
pi = 3.14
```

3. String Variable:
```python
name = "Alice"
```

4. Boolean Variable:
```python
is_student = True
```

5. List Variable (mutable sequence):
```python
fruits = ["apple", "banana", "orange"]
```

6. Tuple Variable (immutable sequence):
```python
coordinates = (10, 20)
```

7. Dictionary Variable (key-value pairs):
```python
person = {"name": "Bob", "age": 30, "city": "New York"}
```

8. Set Variable (unordered collection of unique elements):
```python
unique_numbers = {1, 2, 3, 4, 5}
```

9. None Variable (to represent absence of a value):
```python
result = None
```

10. Complex Variable (complex numbers):
```python
z = 3 + 4j
```

11. Bytes Variable (immutable sequence of bytes):
```python
data = b"hello"
```

12. Bytearray Variable (mutable sequence of bytes):
```python
byte_data = bytearray(b"world")
```

## multiple assignment

Multiple assignments in Python allow you to assign multiple values to multiple variables in a single line. Here are some examples:

1. Assigning multiple values to multiple variables:
```python
x, y, z = 1, 2, 3
```

2. Swapping values between variables:
```python
a, b = 10, 20
a, b = b, a
print("a:", a)  # Output: 20
print("b:", b)  # Output: 10
```

3. Assigning multiple values to a single variable (using unpacking with an iterable):
```python
numbers = [1, 2, 3, 4]
a, b, c, d = numbers
```

4. Assigning multiple values to the same variable:
```python
x = y = z = 0
```

5. Using the * (splat) operator for unpacking:
```python
values = (1, 2, 3, 4, 5)
x, *y, z = values
```
In this case, `x` will be assigned the first value, `z` will be assigned the last value, and `y` will be a list containing the remaining values.

These are some examples of how you can use multiple assignments in Python to assign values to variables efficiently.

## string methods

Here are various methods of strings in Python 3:

#### Case Changing of Strings
- **lower()**: Converts all uppercase characters in a string into lowercase
- **upper()**: Converts all lowercase characters in a string into uppercase
- **title()**: Convert string to title case
- **swapcase()**: Swap the cases of all characters in a string
- **capitalize()**: Convert the first character of a string to uppercase

#### Other String Methods
- **capitalize()**: Converts the first character to upper case
- **casefold()**: Converts string into lower case
- **center()**: Returns a centered string
- **count()**: Returns the number of times a specified value occurs in a string
- **encode()**: Returns an encoded version of the string
- **endswith()**: Returns true if the string ends with the specified value
- **expandtabs()**: Sets the tab size of the string
- **find()**: Searches the string for a specified value and returns the position of where it was found
- **format()**: Formats specified values in a string
- **format_map()**: Formats specified values in a string
- **index()**: Searches the string for a specified value and returns the position of where it was found
- **isalnum()**: Returns True if all characters in the string are alphanumeric
- **startswith()**: Returns true if the string starts with the specified value
- **isalpha()**: Checks if all characters are alphabets
- **isdecimal()**: Checks for decimal characters
- **isdigit()**: Checks for digit characters
- **isidentifier()**: Checks for valid identifier
- **islower()**: Checks if all characters are lowercase
- **isnumeric()**: Checks for numeric characters
- **isprintable()**: Checks if all characters are printable
- **isspace()**: Checks for whitespace characters
- **istitle()**: Checks if each word starts with an upper case letter and the rest are lower case
- **isupper()**: Checks if all characters are uppercase
- **join()**: Joins the elements of an iterable to the end of the string
- **ljust()**: Returns a left-justified version of the string
- **rjust()**: Returns a right-justified version of the string
- **strip()**: Returns a trimmed version of the string
- **lstrip()**: Returns a left trimmed version of the string
- **rstrip()**: Returns a right trimmed version of the string
- **partition()**: Returns a tuple containing the original string, the separator, and the part after the separator
- **replace()**: Replaces a specified value with another value in a string
- **rfind()**: Searches the string for a specified value and returns the last position of where it was found
- **rindex()**: Searches the string for a specified value and returns the last position of where it was found
- **rpartition()**: Returns a tuple containing the part before the separator, the separator, and the part after the separator
- **split()**: Splits the string at the specified separator and returns a list
- **rsplit()**: Splits the string at the specified separator, starting from the right
- **splitlines()**: Splits the string at line breaks and returns a list
- **startswith()**: Returns true if the string starts with the specified value
- **endswith()**: Returns true if the string ends with the specified value
- **swapcase()**: Swaps cases, lower case becomes upper case and vice versa
- **zfill()**: Fills the string with a specified number of 0 values at the beginning
- **format()**: Formats specified values in a string
- **format_map()**: Formats the string using dictionary
- **maketrans()**: Returns a translation table to be used in translations
- **translate()**: Returns a translated string
- **expandtabs()**: Sets the tab size of the string
- **encode()**: Returns an encoded version of the string
- **join()**: Joins the elements of an iterable to the end of the string
- **ljust()**: Returns a left-justified version of the string
- **rjust()**: Returns a right-justified version of the string
- **strip()**: Returns a trimmed version of the string
- **lstrip()**: Returns a left trimmed version of the string
- **rstrip()**: Returns a right trimmed version of the string
- **maketrans()**: Returns a translation table to be used in translations
- **translate()**: Returns a translated string
- **rfind()**: Searches the string for a specified value and returns the last position of where it was found
- **rindex()**: Searches the string for a specified value and returns the last position of where it was found
  - **rpartition()**: Returns a tuple containing the

Certainly! Here are examples of various string methods in Python 3:

1. `upper()`: Converts all characters in a string to uppercase.
```python
string = "hello world"
print(string.upper())  # Output: "HELLO WORLD"
```

2. `lower()`: Converts all characters in a string to lowercase.
```python
string = "HELLO WORLD"
print(string.lower())  # Output: "hello world"
```

3. `capitalize()`: Converts the first character of a string to uppercase and the rest to lowercase.
```python
string = "hello world"
print(string.capitalize())  # Output: "Hello world"
```

4. `title()`: Converts the first character of each word in a string to uppercase.
```python
string = "hello world"
print(string.title())  # Output: "Hello World"
```

5. `strip()`: Removes leading and trailing whitespace characters from a string.
```python
string = "   hello world   "
print(string.strip())  # Output: "hello world"
```

6. `replace()`: Replaces occurrences of a specified substring with another substring.
```python
string = "hello world"
print(string.replace("world", "universe"))  # Output: "hello universe"
```

7. `split()`: Splits a string into a list of substrings based on a delimiter.
```python
string = "apple,banana,orange"
print(string.split(","))  # Output: ['apple', 'banana', 'orange']
```

8. `join()`: Concatenates elements of an iterable (e.g., a list) into a single string, with a specified separator.
```python
words = ["apple", "banana", "orange"]
print(",".join(words))  # Output: "apple,banana,orange"
```

9. `startswith()`: Checks if a string starts with a specified prefix.
```python
string = "hello world"
print(string.startswith("hello"))  # Output: True
```

10. `endswith()`: Checks if a string ends with a specified suffix.
```python
string = "hello world"
print(string.endswith("world"))  # Output: True
```

These are just a few examples of string methods available in Python 3. Python provides many more string methods for various string manipulation tasks.

## type cast
Type casting in Python 3 refers to the process of converting the data type of a variable or value from one type to another. Python provides several built-in functions for type casting, allowing you to convert between different data types as needed. Here are some commonly used type casting functions in Python:

1. **int()**: Converts a value to an integer.
```python
x = 5.7
y = int(x)
print(y)  # Output: 5
```

2. **float()**: Converts a value to a floating-point number.
```python
x = 10
y = float(x)
print(y)  # Output: 10.0
```

3. **str()**: Converts a value to a string.
```python
x = 123
y = str(x)
print(y)  # Output: "123"
```

4. **bool()**: Converts a value to a boolean.
```python
x = 0
y = bool(x)
print(y)  # Output: False
```

5. **list()**: Converts a sequence (e.g., tuple, string) to a list.
```python
tuple_values = (1, 2, 3)
list_values = list(tuple_values)
print(list_values)  # Output: [1, 2, 3]
```

6. **tuple()**: Converts a sequence (e.g., list, string) to a tuple.
```python
list_values = [1, 2, 3]
tuple_values = tuple(list_values)
print(tuple_values)  # Output: (1, 2, 3)
```

7. **set()**: Converts a sequence (e.g., list, tuple) to a set.
```python
list_values = [1, 2, 2, 3, 3]
set_values = set(list_values)
print(set_values)  # Output: {1, 2, 3}
```

8. **dict()**: Converts a sequence of key-value pairs (e.g., list of tuples) to a dictionary.
```python
list_of_tuples = [("a", 1), ("b", 2), ("c", 3)]
dict_values = dict(list_of_tuples)
print(dict_values)  # Output: {'a': 1, 'b': 2, 'c': 3}
```

Type casting is useful when you need to ensure that the data type of a variable matches the requirements of an operation or when you need to convert data between different representations for processing or manipulation.

## user input
In Python 3, you can get user input using the `input()` function. Here are various examples of getting user input in Python 3:

1. **Basic input**: Get a single line of input from the user and assign it to a variable.
```python
name = input("Enter your name: ")
print("Hello,", name)
```

2. **Numeric input**: Convert user input to a numeric data type (int or float) using type casting.
```python
age = int(input("Enter your age: "))
print("You are", age, "years old.")
```

3. **Multiple inputs**: Get multiple inputs from the user and store them in separate variables.
```python
x, y = input("Enter two numbers separated by space: ").split()
x = int(x)
y = int(y)
print("Sum:", x + y)
```

4. **String input**: Get a string input from the user and perform string manipulation.
```python
sentence = input("Enter a sentence: ")
print("Number of characters:", len(sentence))
```

5. **Dynamic input**: Get user input dynamically within a loop until a specific condition is met.
```python
numbers = []
while True:
    num = input("Enter a number (or 'done' to finish): ")
    if num == 'done':
        break
    numbers.append(int(num))
print("Sum of numbers:", sum(numbers))
```

6. **Password input**: Get a password input from the user without displaying the characters entered.
```python
import getpass
password = getpass.getpass("Enter your password: ")
```

These examples demonstrate various ways to get user input in Python 3 for different purposes, including basic input, numeric input, multiple inputs, string input, dynamic input within a loop, and password input.

## math functions
In Python 3, the `math` module provides a wide range of mathematical functions for performing various mathematical operations. These functions cover operations such as arithmetic, trigonometry, exponentiation, logarithms, and more. Here are some common math functions available in Python 3:

1. **Basic Arithmetic Functions**:
   - `math.ceil(x)`: Returns the smallest integer greater than or equal to `x`.
   - `math.floor(x)`: Returns the largest integer less than or equal to `x`.
   - `math.trunc(x)`: Returns the integer part of `x` (truncates the fractional part).
   - `math.factorial(x)`: Returns the factorial of `x`.
   - `math.pow(x, y)`: Returns `x` raised to the power `y`.

2. **Trigonometric Functions**:
   - `math.sin(x)`, `math.cos(x)`, `math.tan(x)`: Returns the sine, cosine, and tangent of `x`, respectively.
   - `math.asin(x)`, `math.acos(x)`, `math.atan(x)`: Returns the arcsine, arccosine, and arctangent of `x`, respectively.
   - `math.degrees(x)`: Converts angle `x` from radians to degrees.
   - `math.radians(x)`: Converts angle `x` from degrees to radians.

3. **Exponential and Logarithmic Functions**:
   - `math.exp(x)`: Returns the exponential of `x` (e^x).
   - `math.log(x)`: Returns the natural logarithm of `x`.
   - `math.log10(x)`: Returns the base-10 logarithm of `x`.
   - `math.log2(x)`: Returns the base-2 logarithm of `x`.

4. **Constants**:
   - `math.pi`: Mathematical constant pi (π).
   - `math.e`: Mathematical constant e (the base of natural logarithms).

5. **Others**:
   - `math.sqrt(x)`: Returns the square root of `x`.
   - `math.isinf(x)`: Returns True if `x` is positive or negative infinity.
   - `math.isnan(x)`: Returns True if `x` is not a number (NaN).

Here's an example demonstrating the usage of some of these functions:

```python
import math

# Basic arithmetic functions
print(math.ceil(4.5))   # Output: 5
print(math.floor(4.5))  # Output: 4
print(math.factorial(5))  # Output: 120
print(math.pow(2, 3))   # Output: 8.0

# Trigonometric functions
print(math.sin(math.pi / 2))  # Output: 1.0
print(math.degrees(math.pi))  # Output: 180.0

# Exponential and logarithmic functions
print(math.exp(2))     # Output: 7.3890560989306495
print(math.log(10))    # Output: 2.302585092994046
print(math.sqrt(25))   # Output: 5.0

# Constants
print(math.pi)  # Output: 3.141592653589793
print(math.e)   # Output: 2.718281828459045
```

These are just a few examples of the many math functions available in Python's `math` module. You can explore the complete list of functions and constants in the official Python documentation.

## string slicing
## if statements
## logical operators
## while loops
## for loops
## nested loops
## reak continue pass
## lists
## 2D lists
## tuples
## sets
## dictionaries
## indexing
## functions
## return statement
## eyword arguments
## nested function calls
## variable scope
## *args
## **kwargs
## string format
## random numbers
## exception handling
## file detection
## read a file
## write a file
## copy a file
## move a file
## delete a file
## modules
## rock, paper, scissors game
## quiz game
## Object Oriented Programming (OOP)
## class variables
## inheritance
## multilevel inheritance
## multiple inheritance
## method overriding
## method chaining
## super function
## abstract classes
## objects as arguments
## duck typing
## (04:27:38) walrus operator
## functions to variables
## higher order functions
## lambda
## sort
## map
## filter
## reduce
## list comprehensions
## dictionary comprehensions
## zip function
## if name == '__main__'
## time module
## threading
## daemon threads
## multiprocessing
## GUI windows
## labels
## buttons
## entrybox
## checkbox
## radio buttons
## scale
## listbox
## messagebox
## colorchooser
## text area
## open a file (file dialog)
## save a file (file dialog)
## menubar
## frames
## new windows
## window tabs
## grid
## progress bar
## canvas
## keyboard events
## mouse events
## drag & drop
## move images w/ keys
## animations
## multiple animations
## clock program
## send an email
## run with command prompt
## pip
## py to exe
## calculator program
## text editor program
## tic tac toe game
## snake game
