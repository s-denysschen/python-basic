# The Basics of Python
<hr>
# Table of Contents
1. [Installation](#installing-python-and-anaconda)
2. [The very basics](#basic-terminology-and-data-types-of-python)
3. [Controlling program flow](#flow-control)
4. [Functions](#functions)
5. [Variable scope](#global-and-local-scope)
6. [Lists](#lists)
7. [Dictionaries](#dictionaries)
8. [Some more stuff about strings](#advanced-strings)
9. [Regular expressions](#regular-expressions)
10. [Working with files](#files)
11. [Debugging](#debugging)
12. [Web scraping](#web-scraping)
13. [Excel, Word & PDFs](#excel-word-and-pdf-documents)
<hr>
## Installing Python and Anaconda
Hey there! Welcome to a begginer's guide to the world of the most intuitive programming language - Python! Let's get our tools ready.
### Python Installation
First things first, we need to install Python. It's not hard:
* Go to the Python downloads page at https://www.python.org/downloads/.
* Download the latest Python version (Python 3.x.x, the exact version changes all the time).
* Run the installer, and make sure to check the box that says "Add Python 3.x to PATH" before you click on "Install Now", or manually add the Pythin bin folder to your environment and system variables. 
* That's it!
### Anaconda Installation
Next, we gotta install Anaconda. It's a distribution of Python that comes with a lots of nifty libraries and tools:
* Head to the Anaconda download page at https://www.anaconda.com/products/distribution#download-section.
* Download the Python 3.x version.
* Run the installer and follow the instructions.
### Jupyter Notebook
Anaconda comes with Jupyter Notebook, an open-source web-app that allows you to create and share documents that contain live code, equations, visualizations, narrative text, and more. To start Jupyter Notebook:
* Open Anaconda Navigator (it gets installed with Anaconda).
* Click on the Jupyter Notebook icon (pro tip: pin to taskbar for quicker launch).
* Code along with a simple, shareable and interactive interface!
<hr>
## Basic terminology and data types of Python
Let's look at Python's basic terminology and data types.
### Python's Basic Terminology
* Syntax: This refers to the set of rules that define how Python programs are written and interpreted.
* Variable: A name that refers to a value.
* Function: A reusable piece of code that performs a specific task.
* Module: A file containing Python definitions and statements. It allows you to logically organize your Python code.
* Library: A collection of modules.
### Data Types
* Python has several built-in data types:
* Numeric Types: These include integers (`int`), floating point numbers (`float`), and complex numbers (`complex`).
* Sequence Types: These include strings (`str`), lists (`list`), and tuples (`tuple`).
* Mapping Type: This includes dictionaries (`dict`).
* Boolean Type: This includes `True` and `False`.
Here's a small piece of code illustrating these data types:
```python
# Numeric Types
x = 10     # int
y = 3.14   # float
z = 3 + 4j # complex

# Sequence Types
s = "hello"          # str
lst = [1, 2, 3, 4]   # list
tup = (1, 'a', True) # tuple

# Mapping Type
d = {'name': 'Alice', 'age': 20} # dict

# Boolean Type
b1 = True  # True
b2 = False # False
```
### A Simple Python Program
Welcome back! Now that we've got Python installed and we understand some basic terminology and data types, let's write our first Python program. Let's write a simple program that asks for your name and age, and then prints a message. It's a tradition to start programming with a "Hello, World!" program, but let's do something a bit more interactive.
```python
# This is a simple Python program

# Ask for user's name
name = input("What's your name? ")

# Ask for user's age
age = int(input("How old are you?"))

# Calculate birth year
import datetime
year_of_birth = datetime.datetime.today().year - age

# Print a message
print(f"Hello {name}! Since you are {str(age)} years old, that implies you were born about {str(year_of_birth)}.")
```
In this code:
* We're using the `input()` function to get user input.
* We import the `datetime` library and use its `datetime.today()` function and `.year` attribute to extract the current year in integer format.
* The `print()` function is used to print the output.
* The `int()` and `str()` are warpper functions that convert variables to integer ans tring types, respectively.
* The f-string (formatted string literal) is used to include variables inside the printed string.
That's it! Notice the concise and readable nature of Python. A lot gets done in a few lines, and it's intuitive to follow along.
<hr>
## Flow Control
Now we're getting into flow control - i.e. the order in which your code executes. Let's start with an overview and a useful tool: flowcharts.
### Flow Control
Flow control refers to the order in which the program's code executes. It might go in order, skip over some code, or keep repeating a block of code - this all depends on the flow control statements.
### Flowcharts
Flowcharts are diagrams that visually represent a process or a program. They're great for planning your program's flow control before you start coding.
The most common symbols in flowcharts are:
* Oval: Start or end of a program.
* Rectangle: A command or operation.
* Diamond: A decision or condition.
Let's illustrate this with a simple program that checks if a number is positive or negative.
```python
# Start
#   |
#   V
# Read number
#   |
#   V
# Is number >= 0?
#   |
#   V
# Yes     No     
# /       \
# Print "Positive"  Print "Negative"
#   |                    /
#   V                   /
# End  <---------
```
Now, let's implement it in Python!
### If, Else, and Elif
Let's implement our flowchart with Python's flow control statements - `if`, `else`, and `elif`.
```python
# Ask for a number
number = float(input("Enter a number: "))

# Check if the number is positive or negative
if number > 0:
    print("Positive")
else:
    print("Negative")
```
In this code:
* `if` checks the condition (`number > 0`). If it's `True`, it executes the following indented block of code.
* `else` executes its indented block of code if the `if` condition is `False`.
But what if we want to check for more conditions? That's where `elif` (else if) comes in. Let's modify our code to also check if the number is zero:
```python
# Ask for a number
number = float(input("Enter a number: "))

# Check if the number is positive, negative, or zero
if number > 0:
    print("Positive")
elif number < 0:
    print("Negative")
else:
    print("Zero")
```
In this code, `elif` checks another condition if the previous conditions are `False`. If `number > 0` and `number < 0` are both `False`, the `else` block executes.
### While Loops
These allow a block of code to repeat as long as a condition is `True`.
```python
# Start from 0
number = 0

# Keep printing the number while it's less than 5
while number < 5:
    print(number)
    number = number + 1
```
In this code:
* The `while` loop checks the condition (`number < 5`). If it's `True`, it executes the indented block of code and then checks the condition again.
* This repeats until the condition is False.
### For Loops
Let's look at for-loops. They're like while loops, but they iterate over a sequence (like a `list`, `tuple`, `dict`, `set`, or `str`).
```python
# A list of names
names = ["Alice", "Bob", "Charlie", "Dave"]

# Print each name using a for loop
for name in names:
    print(name)
```
In this code:
* The `for` loop goes through each item in names.
* For each item, it executes the indented block of code (printing the name).
<hr>
## Functions
### Built-in Functions
Python comes with many built-in functions. Here are a few examples:
* `print()`: This function prints the specified message to the screen.
* `input()`: This function waits for user input.
* `len()`: This function returns the length (the number of items) of an object.
* `type()`: This function returns the type of an object.
* `max()`: This function returns the largest item in an iterable or the largest of two or more arguments.
* `min()`: This function returns the smallest item in an iterable or the smallest of two or more arguments.
* `abs()`: This function returns the absolute value of a number.
* `sum()`: This function takes an iterable and an optional start value (default is 0), and adds up the iterable's elements from left to right, then adds the start value.
Here's some code illustrating these functions:
```python
# print
print("Hello, world!")
# input
name = input("What's your name? ")
# len
name_length = len(name)
print(f"Your name has {name_length} characters.")
# type
name_type = type(name)
print(f"Your name is of type {name_type}.")
numbers = [1, 2, 3, 4, 5]
# max
print(max(numbers)) # prints: 5
# min
print(min(numbers)) # prints: 1
# abs
print(abs(-10)) # prints: 10
# sum
print(sum(numbers)) # prints: 15
```
### Writing Custom Functions
Custom functions are great for when you need to perform a specific task multiple times in your code. Here's how you create one:
```python
def greet(name):
    print(f"Hello, {name}!")
```
In this code:
* `def` is a keyword that starts the function definition.
* `greet` is the name of the function.
* `name` is a parameter - a value that the function expects you to pass when you call it.
* `print(f"Hello, {name}!")` is the body of the function - the code that runs when you call the function.
To call this function:
```python
greet("Sjarko")
```
##### Nested Functions
A nested function is a function defined inside another function. They're useful when you want to encapsulate some logic that you only need to use within another function.
```python
def outer_function(name):
    # This is a nested function
    def inner_function():
        return name.title() # Capitalize initial
        
    greeting = f"Hello, {inner_function()}!"
    print(greeting)
outer_function("sjarko")
```
In this code:
* `inner_function()` is a nested function. It's defined inside `outer_function()`.
* `inner_function()` makes the first character of name uppercase.
* `outer_function(name)` calls the outer function, which in turn calls `inner_function()`, and prints `"Hello, [name]!"`.
#### Recursive functions
A recursive function is a function that calls itself during its execution. This enables the function to be repeated several times, as it can call itself during its execution. Recursive functions are often used to solve problems that can be broken down into simpler, repetitive tasks.
Here is an example of a recursive function that calculates the factorial of a number. Factorial of a number is the product of all positive integers up to that number. For instance, the factorial of 5 (denoted as 5!) is 1 * 2 * 3 * 4 * 5 = 120.
```python
def factorial(n):
    # Base case: 1! = 1
    if n == 1:
        return 1
    # Recursive case: n! = n * (n-1)!
    else:
        return n * factorial(n-1)
print(factorial(5))  # Output: 120
```
In this code:
* The function `factorial(n)` takes an integer `n` as input.
* If `n` is 1 (the base case), the function returns 1. This is the simplest form of the problem, where we know the answer without needing any further recursive calls.
* If `n` is not 1, the function calls itself to calculate the factorial of `n` - 1, then multiplies this result by `n` to give the factorial of `n`.
It's important to have a base case in a recursive function to ensure that the recursion stops at some point. Without a base case, a recursive function would call itself indefinitely.
<hr>
## Global and Local Scope
### Scope
The scope of a variable is the part of a program where that variable can be accessed. There are two types of scope:
* Global scope: The main body of a script. A variable defined in the global scope is a global variable, and can be accessed anywhere in the code.
* Local scope: Inside a function. A variable defined in the local scope is a local variable, and can only be accessed inside that function.
Here's an example:
```python
# This is a global variable
greeting = "Hello"

def greet(name):
    # This is a local variable
    exclamation = "!"
    print(f"{greeting}, {name}{exclamation}")

greet("Sjarko")
```
In this code:
* `greeting` is a global variable. It can be accessed anywhere, including inside the `greet()` function.
* `exclamation` is a local variable. It can only be accessed inside the `greet()` function. Trying to access the exclamation variable outside of the function will raise a `NameError`.
<hr>
## Lists
### List Datatype
A list in Python is an ordered collection of items, which can be of any type. Items in a list are enclosed in square brackets `[]` and separated by commas. Here's an example:
```python
# This is a list
fruits = ["apple", "banana", "cherry", "date"]
```
In this code, `fruits` is a list that contains four strings.
To access an item in a list, you use its index. Indices in Python start from 0, so to get the first fruit (`"apple"`), you would write `fruits[0]`.
```python
### For Loops with Lists
You can use a for loop to go through each item in a list:
# Print each fruit
for fruit in fruits:
    print(fruit)
### Multiple Assignment
```
You can assign values to multiple variables at once using a list:
```python
# Assign values to variables
fruit1, fruit2, fruit3, fruit4 = fruits
```
Now `fruit1` is `"apple"`, `fruit2` is `"banana"`, etc.
### Augmented Operators
You can use augmented operators like `+=` to modify list items:
```python
# Start with an empty list
numbers = []

# Add numbers to the list
for i in range(5):
    numbers += [i]

print(numbers)
```
### List Methods
List methods are built-in functions that you can use with lists.
Here are a few list methods:
* `append()`: Adds an item to the end of the list.
* `insert()`: Adds an item at a specified position.
* `remove()`: Removes a specified item.
* `pop()`: Removes the item at a specified position.
Here's some code illustrating these methods:
```python
# Start with an empty list
fruits = []

# Add fruits
fruits.append("apple")
fruits.append("banana")
fruits.insert(1, "cherry")

# Remove and pop fruits
fruits.remove("apple")
fruits.pop(1)

print(fruits)
```
### List-String Similarities
Strings and lists in Python are both sequences, so they share several features:
* You can access their items using indices (`"hello"[0]` and `[1, 2, 3][0]`).
* You can slice them to get sub-sequences (`"hello"[1:3]` and `[1, 2, 3][1:3]`).
* You can use `len()` to get their length (`len("hello")` and `len([1, 2, 3])`).
However, there's a key difference: strings are immutable (you can't change their characters), but lists are mutable (you can change their items).
<hr>
## Dictionaries
### Dictionary Data Type
A dictionary in Python is an unordered collection of items. Unlike lists, which are indexed by a range of numbers, dictionaries are indexed by keys, which can be any immutable type. Dictionaries are enclosed by curly braces `{}`. Each item in a dictionary is a pair of a key and a value. The key and value are separated by a colon `:`.  Different items are separated by commas. Here's an example:
```python
# This is a dictionary
employee = {
    "name": "Sjarko",
    "age": 27,
    "title": "Data scientist"
}
```
To access a value in a dictionary, you use its key. So to get an employee's age, you would write `employee["age"]`.
### Adding and Modifying Dictionary Items
You can add an item to a dictionary by assigning a value to a new key:
```python
# Add a new item
employee["department"] = "Customer Service"
```
You can modify an item in a dictionary by assigning a new value to its key:
```ptyhon
# Modify an item
employee["title"] = "Machine learning engineer"
```
You can remove an item from a dictionary using the `del` statement:
```python
# Remove an item
del employee["age"]
```
### Data Structures
A data structure is a collection of data elements that is structured in some way. Lists, tuples, sets, and dictionaries are all types of data structures in Python. Different data structures are suitable for different tasks.
A data structure can also contain other data structures. For example, our `employee` dictionary can contain a list:
```python
# This is a dictionary with a list
employee = {
    "name": "Alice",
    "department": "Sales",
    "targets": [90, 95, 88]
}
```
A dictionary can also contain other dictionaries. This is known as a nested dictionary. For example, we could have a dictionary of `employees`:
```python
# This is a dictionary of dictionaries
employee = {
    "Alice": {
        "age": 72,
        "targets": [90, 95, 88]
    },
    "Sjarko": {
        "age": 27,
        "projects": ['NLP', 'MLOps', 'CVM']
    }
}
```
To access a value in a nested dictionary, you use the keys of the outer and inner dictionaries. 
```python
employee["Sjarko"]["projects"]
```
<hr>
## Advanced Strings
Python supports several ways of writing strings:
* Single quotes: `'hello'`
* Double quotes: `"hello"`
* Triple quotes: `'''hello'''` or `"""hello"""`
* You can use either single or double quotes for short strings. If your string contains a quote character, you can use the other type of quote to define it:
```python
# This string contains a single quote
string = 'It's a beautiful day.'
```
Triple quotes are used for multiline strings:
```python
# This is a multiline string
string = """Hello,
world!"""
```
### Escape Sequences
You can use escape sequences to insert special characters into a string. An escape sequence starts with a backslash \ followed by the character you want to insert.
Here are some common escape sequences:
* `\'`: Single quote
* `\"`: Double quote
* `\n`: Newline
* `\t`: Tab
Here's an example:
```python
# This string uses escape sequences
string = "She said, \n'Hello, \tworld!'"
print(string)
```
### String Methods
Here are a few string methods:
* `upper()`: Returns a copy of the string with all the characters in uppercase.
* `lower()`: Returns a copy of the string with all the characters in lowercase.
* `find()`: Returns the index of the first occurrence of a substring. If the substring is not found, returns -1.
* `replace()`: Returns a copy of the string with all occurrences of a substring replaced with another substring.
Here's some code illustrating these methods:
```python
# Start with a string
string = "Hello, world!"

# Use string methods
upper_string = string.upper()
lower_string = string.lower()
index = string.find("world")
replaced_string = string.replace("world", "Sjarko")
```
### String Formatting
You can use the `format()` method to insert variables into a string. The index of the variable in the call to the `format()` method corresponds to the index of the empty tuple to fill inside of the string:
```python
# Use the format method
name = "Sjarko"
age = 27
greeting = "Hello, {}, you are {} years old".format(name,age)
print(greeting)
```
You can also cast non-string variable to string type with the `str()` funtion, then use simple addition to insert the variable into the string:
```python
# Use the addition method
name = "Sjarko"
age = 27
greeting = "Hello, " + name + ", you are " + str(age) + " years old."
print(greeting)
```
f-strings are a more convenient way to format strings:
```python
# Use an f-string with an expression
name = "Sjarko"
age = 27
greeting = f"Hello, {name}, you are {age} years old."
print(greeting)
```
<hr>
## Regular Expressions
### Basics of Regular Expressions
Regular expressions are a way of describing patterns in string data. They're a powerful tool for manipulating text. Python's `re` module provides support for regular expressions.
First, you'll need to import the `re` module:
```python
import re
```
To create a regex object, use the `re.compile()` function:
```python
# This is a regex object
regex = re.compile('abc')
```
This object represents the pattern 'abc'.
You can use the `search()` method to search for this pattern in a string:
```python
# Search for the pattern
match = regex.search('abcdef')
```
This method returns a match object, which contains information about the match. If the pattern is not found, the method returns `None`.
You can use the `group()` method of the match object to get the actual matched text:
```python
# Print the matched text
print(match.group())
```
### Regex Groups and The Pipe Character
#### Regex Groups
You can define groups in a regex pattern using parentheses. For example, the pattern (abc) defines a group containing the pattern 'abc'.
```python
# This regex has a group
regex = re.compile('(abc)')
```
The `group()` method of the match object can take an argument to return the text of a specific group. `group(0)` returns the entire match, `group(1)` returns the first group, and so on.
#### The Pipe Character
The pipe character `|` represents "or". It matches either the pattern before it or the pattern after it.
```python
# This regex matches either 'abc' or 'def'
regex = re.compile('abc|def')
```
This regex matches either 'abc' or 'def'.
### Repetition in Regex Patterns and Greedy/Nongreedy Matching
#### Repetition in Regex Patterns
There are several characters that can represent repetition:
* `*`: Zero or more times.
* `+`: One or more times.
* `?`: Zero or one time.
* `{n}`: Exactly n times.
* `{n,}`: n or more times.
* `{,m}`: m or fewer times.
* `{n,m}`: Between n and m times.
Here's an example:
```python
# This regex matches one or more 'a's
regex = re.compile('a+')
```
#### Greedy and Nongreedy Matching
By default, Python's regex are greedy: they match the longest possible string. You can make them nongreedy (matching the shortest possible string) by following the repetition character with a `?`.
```python
# This regex matches as few 'a's as possible
regex = re.compile('a+?')
```
### Regex Character Classes and the findall() Method
#### Regex Character Classes
A character class matches any character in the class. Here are some predefined character classes:
* `\d`: Any digit (0-9).
* `\D`: Any non-digit.
* `\s`: Any whitespace character.
* `\S`: Any non-whitespace character.
* `\w`: Any alphanumeric character (a-z, A-Z, 0-9, _).
* `\W`: Any non-alphanumeric character.
```python
# This regex matches any digit
regex = re.compile('\d')
```
#### The `findall()` Method
The `findall()` method returns all matches of a pattern in a string, as a list of strings. The strings will be in the order they were found.
```python
# Find all matches
matches = regex.findall('123 abc 456 def')
```
### Regex Dot-Star and The Caret/Dollar Characters
#### The Dot-Star
In regex, the dot `.` matches any character except a newline. The star `*` matches zero or more repetitions of the preceding character. Together, `.*` matches any number of any characters.
```python
# This regex matches any number of any characters
regex = re.compile('.*')
```
#### The Caret and Dollar Characters
The caret `^` matches the start of the string, and the dollar `$` matches the end of the string.
```python
# This regex matches a string that starts with 'abc' and ends with 'def'
regex = re.compile('^abc.*def$')
```
### Regex `sub()` Method and Verbose Mode
#### The `sub()` Method
The `sub()` method replaces all matches of a pattern with a replacement string:
```python
# Replace all matches
regex = re.compile('\d')
new_string = regex.sub('X', '123 abc 456 def')
```
#### Verbose Mode
Verbose mode allows you to write regex that's easier to read and understand. You can add comments and whitespace to your regex.
```python
# This regex is in verbose mode
regex = re.compile('''
    ^    # Start of the string
    abc  # 'abc'
    .*   # Any number of any characters
    def  # 'def'
    $    # End of the string
''', re.VERBOSE)
```
<hr>
## Files
### Filenames and Absolute/Relative File Paths
A file path describes the location of a file in a computer's file system.
* Absolute file paths: These provide the complete detail, starting from the root directory to the specific file. For example, /home/user/documents/myfile.txt is an absolute file path in Unix/Linux, and C:\\Documents\\myfile.txt is an absolute file path in Windows.
* Relative file paths: These start from the current working directory. For example, if the current directory is /home/user, the relative path to myfile.txt in the documents directory would simply be documents/myfile.txt.
Python's `os` module provides several functions to work with file paths. You can use `os.path.abspath(path)` to get the absolute path of a file and `os.path.relpath(path)` to get the relative path.
```python
import os
# Get the absolute path of a file
abs_path = os.path.abspath('documents/myfile.txt')
# Get the relative path of a file
rel_path = os.path.relpath('/home/user/documents/myfile.txt')
```
### Reading and Writing Plaintext Files
Python provides built-in functions for reading and writing files.
To open a file, use the `open()` function. This function takes two arguments: the file path and the mode. The mode can be `'r'` for read mode, `'w'` for write mode, `'a'` for append mode, and `'r+'` for both reading and writing.
Here's an example of opening a file for reading:
```python
# Open a file for reading
file = open('myfile.txt', 'r')
```
To read the contents of the file, you can use the `read()` method:
```python
# Read the file
contents = file.read()
```
To write to a file, open it in write mode and use the `write()` method:To write to a file, open it in write mode and use the `write()` method:
```python
# Open a file for writing
file = open('myfile.txt', 'w')

# Write to the file
file.write('Hello, world!')
```
Don't forget to close the file when you're done with it!
```python
# Close the file
file.close()
```
### Copying and Moving Files and Folders
Python's `shutil` module provides functions to copy and move files and folders.
Here's an example of copying a file:
```python
import shutil

# Copy a file
shutil.copy('myfile.txt', 'mycopy.txt')
And here's an example of moving a file:
# Move a file
shutil.move('myfile.txt', 'myfolder/myfile.txt')
```
### Deleting Files
Python's `os` module provides functions to delete files. The `os.remove()` function deletes a file:
```python
import os
# Delete a file
os.remove('myfile.txt')
```
To delete an empty folder, you can use `os.rmdir()`. To delete a folder and all its contents, you can use `shutil.rmtree()`.
### Walking a Directory Tree
Walking a directory tree involves visiting a directory and all its subdirectories, recursively. Python's `os` module provides the `os.walk()` function for this purpose.
```python
import os
# Walk a directory tree
for dirpath, dirnames, filenames in os.walk('mydirectory'):
    print('Directory:', dirpath)
    for filename in filenames:
        print('File:', filename)
```
This code prints the names of all directories and files in 'mydirectory' and its subdirectories.
<hr>
## Debugging
### The raise and assert Statements
#### The raise Statement
Sometimes, you might need to create an error yourself, possibly to notify other parts of your program that something has gone wrong. Python allows you to create exceptions using the `raise` statement.
```python
# Raise an exception
raise Exception('This is an error message.')
```
#### The assert Statement
An assertion is a sanity check to make sure your code isn’t doing something obviously wrong. If the sanity check fails, then an `AssertionError` exception is raised.
```python
# Assert statement
assert 2 + 2 == 4, 'Math still works.'
```
### Logging
Python's logging module provides a way to display log messages. Log messages provide a way to understand the activities of a running program.
To use the logging module, you first need to import it:
```python
import logging
```
You can use the `logging.debug()`, `logging.info()`, `logging.warning()`, `logging.error()`, and `logging.critical()` functions to display log messages:
```python
# Display a log message
logging.debug('This is a debug message.')
```
### Using the Debugger
Python's `pdb` module provides a debugger. You can use the debugger to step through your code, examine values of variables, and find where your code is going wrong.
To use the debugger, you first need to import the `pdb` module:
```python
import pdb
```
You can set a breakpoint in your code using the `pdb.set_trace()` function. When your code reaches this point, it will pause and let you step through the code.
```python
# Set a breakpoint
pdb.set_trace()
```
When your code is paused, you can use various commands to navigate through your code. Some of the most useful commands are:
* `n` (next): Execute the next line.
* `s` (step): Step into a function call.
* `c` (continue): Continue execution until the next breakpoint.
* `p` (print): Print the value of an expression.
<hr>
## Web scraping
### The `webbrowser` module
Python's `webbrowser` module provides a high-level interface to allow displaying web-based documents to users. It comes pre-installed with Python, so you don't need to install it.
One of the simplest tasks you can do with the `webbrowser` module is opening a web page in a new browser window:
```python
import webbrowser

# Open a web page
webbrowser.open('https://www.python.org')
```
This code launches a web browser to the Python homepage.
### Downloading from the Web with the `requests` module
Python's `requests` module allows you to send HTTP requests. It simplifies the process of working with HTTP requests and handles the complexities of HTTP protocols behind the scenes.
To use the `requests` module, you first need to install it:
```python
pip install requests
```
Here's an example of downloading a web page:
```python
import requests

# Download a web page
response = requests.get('https://www.python.org')

# Print the content of the page
print(response.text)
```
This code downloads the Python home page and prints its HTML content.
### Parsing HTML with the `Beautiful Soup` Module
`Beautiful Soup` is a Python library for parsing HTML and XML documents. It creates a parse tree from page source code that can be used to extract data in a hierarchical and more readable manner.
To use `Beautiful Soup`, you first need to install it:
```python
pip install beautifulsoup4
```
Here's an example of parsing an HTML document:
```python
from bs4 import BeautifulSoup

# Parse an HTML document
soup = BeautifulSoup('<html><body><h1>Hello, world!</h1></body></html>', 'html.parser')

# Find the h1 tag
h1_tag = soup.find('h1')

# Print the text of the h1 tag
print(h1_tag.text)
```
This code parses an HTML document, finds the `h1` tag, and prints its text.
### Controlling the Browser with the `Selenium` Module
`Selenium` is a powerful tool for controlling a web browser through the program. It's functional for all browsers, works on all major OS and its scripts are written in various languages i.e Python, Java, C#, etc.
To use `Selenium`, you first need to install it:
```python
pip install selenium
```
In order to have a working setup, you will also need a driver, which is a separate executable that Selenium WebDriver uses to control the browser. The driver depends on the browser you want to use. For example, if you want to use Chrome, you need the ChromeDriver.
Here's an example of opening a web page with `Selenium`:
```python
from selenium import webdriver

# Create a new instance of the Firefox driver
driver = webdriver.Chrome()

# Go to a web page
driver.get('https://www.python.org')

# Find the element that's name attribute is q (the Google search box)
input_element = driver.find_element_by_name('q')

# Type in the search
input_element.send_keys('Python')

# Submit the form (although google automatically searches now without submitting)
input_element.submit()

# Close the browser
driver.quit()
```
This code opens the Python home page in Google Chrome, types 'Python' in the search box, and submits the search. You need to have the ChromeDriver executable installed and in your system's PATH for this to work. You can download ChromeDriver from the ChromeDriver download page and add its location to your system's PATH.
<hr>
## Excel, Word, and PDF Documents
### Reading Excel Spreadsheets
Python's `openpyxl` module allows you to read and write Excel xlsx/xlsm/xltx/xltm files.
To use the `openpyxl` module, you first need to install it:
```python
pip install openpyxl
```
Here's an example of reading an Excel spreadsheet:
```python
from openpyxl import load_workbook

# Load a workbook
wb = load_workbook('mydocument.xlsx')

# Select a worksheet
ws = wb['Sheet1']

# Print the value of a cell
print(ws['A1'].value)
```
This code reads the Excel document 'mydocument.xlsx', selects the worksheet 'Sheet1', and prints the value of cell A1.
### Editing Excel Spreadsheets
You can also use the `openpyxl` module to edit Excel spreadsheets.
Here's an example of editing an Excel spreadsheet:
```python
from openpyxl import load_workbook

# Load a workbook
wb = load_workbook('mydocument.xlsx')

# Select a worksheet
ws = wb['Sheet1']

# Change the value of a cell
ws['A1'] = 'Hello, world!'

# Save the workbook
wb.save('mydocument.xlsx')
```
This code edits the Excel document 'mydocument.xlsx', changes the value of cell A1 to 'Hello, world!', and saves the document.
### Reading and Editing PDFs
#### Reading PDFs
Python's `PyPDF2` module allows you to read PDF files.
To use the `PyPDF2` module, you first need to install it:
```python
pip install PyPDF2
```
Here's an example of reading a PDF:
```python
import PyPDF2

# Open a PDF
with open('mypdf.pdf', 'rb') as file:
    reader = PyPDF2.PdfFileReader(file)

    # Print the content of the first page
    print(reader.getPage(0).extractText())
```
This code reads the PDF document 'mypdf.pdf' and prints the content of the first page.
#### Editing PDFs
You can use `PyPDF2` to perform simple operations like splitting, merging, and rotating pages. However, `PyPDF2` cannot write text to a PDF. For that purpose, you'd need a module like `reportlab`.
```python
pip install reportlab
```
Then you can use the following code to create a PDF:
```python
from reportlab.pdfgen import canvas

# Create a new PDF file
c = canvas.Canvas("new_pdf.pdf")

# Write some text
c.drawString(100, 750, "Hello, world!")

# Save the PDF
c.save()
```
In this example, a new PDF file named "new_pdf.pdf" is created. The text `"Hello, world!"` is written to the file at the coordinates (100, 750) from the bottom-left corner of the page.
`reportlab` can only create new PDFs and write to them. If you want to edit existing PDFs, you will need to use a combination of `PyPDF2` (to read the existing PDF) and `reportlab` (to write the new content). Here's an example:
```python
from PyPDF2 import PdfFileReader, PdfFileWriter
from reportlab.pdfgen import canvas
from reportlab.lib.pagesizes import letter
from io import BytesIO

# Load the existing PDF
with open("existing_pdf.pdf", "rb") as file_handle:
    pdf = PdfFileReader(file_handle)
    page = pdf.getPage(0)
    packet = BytesIO()

    # Create a new PDF with Reportlab
    can = canvas.Canvas(packet, pagesize=letter)
    can.drawString(100, 750, "Hello, world!")
    can.save()

    # Move to the beginning of the StringIO buffer
    packet.seek(0)
    new_pdf = PdfFileReader(packet)

    # Add the "watermark" (which is the new pdf) on the existing page
    page.mergePage(new_pdf.getPage(0))
    output = PdfFileWriter()

    # Add the page from the existing PDF to the output file
    output.addPage(page)

    # Write the output file
    with open("output.pdf", "wb") as output_pdf:
        output.write(output_pdf)
```
In this example, the existing PDF file named "existing_pdf.pdf" is opened. A new PDF file with the text "Hello, world!" is created with `reportlab` and overlaid on the existing PDF. The result is saved to "output.pdf". Note that the original PDF file is unchanged; a new PDF file is created with the modifications.
### Reading and Editing Word Documents
Python's `python-docx` module allows you to read and write Word documents.
To use the `python-docx` module, you first need to install it:
```python
pip install python-docx
```
Here's an example of reading a Word document:
```python
from docx import Document

# Open a Word document
doc = Document('mydocument.docx')

# Print the content of the first paragraph
print(doc.paragraphs[0].text)
```
Here's an example of editing a Word document:
```python
from docx import Document

# Open a Word document
doc = Document('mydocument.docx')

# Add a paragraph
doc.add_paragraph('Hello, world!')

# Save the document
doc.save('mydocument.docx')
```
These code snippets read and edit the Word document 'mydocument.docx' respectively. 
<hr>
That about wraps it up for the very basics of Python. Be sure to check out other parts of my Hub fo more advanced Python sorcery.
