### Basics Python Questions

#### Q.1 Difference between == and "is"
```bash
==  operator helps us compare the equality of objects
is  operator used to test if two variables refer to the same object
a = [1, 2, 3]
b = [1, 2, 3]

print(a == b)  # values same
print(a is b)  # memory different

o/p -
True
False
```

#### Q.2 How to delete a key from a dictionary ?
```bash
del 
del dict_name[‘key_name’]

pop
dict_name.pop[‘key_name’]
```

#### Q.3 How to remove item from list ? 
```bash
remove()
remove(list_value)

del
del list_name[index_value]

pop()
list_name.pop[index_value]
```

#### Q.4 What is a decorator in python?
```bash
Decorator allow to change the behavior  of function or class without any modification.
The outer function is called the decorator, which takes the original function as an argument and returns a 
modified version of it.
```

#### Q.5. What is a lambda function in python ?
```bash
A lambda function can take any number of arguments, but can only have one expression.
Ex :- lambda a : a + 10

x = lambda a : a + 10
print(x(5))

x = lambda a, b : a * b
print(x(5, 6))
 
A lambda function is an anonymous function (a function that does not have a name) in Python. 
To define anonymous functions, we use the ‘lambda’ keyword instead of the ‘def’ keyword, hence the name 
‘lambda function’. Lambda functions can have any number of arguments but only one statement.
```

#### Q.6 What is a list comprehension in python ? 
```bash
when you want to create a new list based on the values of an existing list

arr = [1,2,3,4,5,6,7,8,9]
new_list = [x for x in range(len(arr)) if x%2 == 0]
```

#### Q.7. What is the difference between a tuple and a list in Python?
```bash
List is mutable and tuple immutable 
Iteration slow in list and in tuple fast
Memory consume more in list as compare to tuple
```

#### Q.8. What does “self” refer to in a class?
```bash
Self represents the instance of the class. By using the “self” we can access the attributes 
and methods of the class in Python. It binds the attributes with the given arguments.
```

#### Q.9 What are negative indexes and why are they used?
```bash
Negative indexing is used in Python to manipulate sequence objects such as lists, arrays, strings, etc. Negative indexing retrieves elements from the end by providing negative numbers as sequence indexes.
```

#### Q.10. What is the difference between a module and a package in python ?
```bash
module is a single file containing python code, whereas a package is a collection of modules that are
organized in a directory hierarchy
```

#### Q.11.	When to use the assert keyword in python? What does it do
```bash
The assert keyword is used when debugging code.The assert keyword lets you test if a condition in your 
code returns True, if not, the program will raise an AssertionError.You can write a message to be written if the code returns False.
```

#### Q-12 what is difference between multi proccessing and multi thrading 
```bash 
Multiprocessing is used to create a more reliable system, whereas multithreading is used to 
create threads that run parallel to each other
```

#### Q-13 what is GIL in python
```bash 
The Python Global Interpreter Lock or GIL, in simple words, is a mutex (or a lock) that allows 
only one thread to hold the control of the Python interpreter.

Basically, GIL in Python doesn’t allow multi-threading which can sometimes be considered as a disadvantage. 

Python has a multi-threading package but commonly not considered a good practice to use 
it as it results in increased code execution time.

Python has a constructor called the Global Interpreter Lock (GIL). The GIL ensures that only one 
of your ‘threads’ can execute at one time. The process makes sure that a thread acquires the GIL, 
does work, then passes the GIL onto the next thread.
```
#### Q-13 whats is difference between call by reference and call by value
```bash 
in python there is there no concept because python treat everything as a object
call by value > when ever you call a function with calling a variable value not the address 
call by reference >  when ever you call a function with calling a variable  by address 
```

#### Q-14 what is dunder method what is differance between functions and methods
```bash 
Dunder or Magic methods in Python are the methods having two prefixes and suffix underscores in the method name. 
Dunder here means “Double Under (Underscores)”. These are commonly used for operator overloading. 

A function doesn't need any object and is independent, while the method is a function, which is linked with any object. 
We can directly call the function with its name, while the method is called by the object's name. 
Function is used to pass or return the data, while the method operates the data in a class.
```

#### Q-15 what is differance between iterator and genratore ?  
```bash 
An iterator is an object which contains a countable number of values and it is used to iterate over 
iterable objects like list, tuples, sets, etc. 

iter() keyword is used to create an iterator containing an iterable object.
next() keyword is used to call the next element in the iterable object.

It is another way of creating iterators in a simple way where it uses the keyword “yield” instead 
of returning it in a defined function. 
```

#### Q-16 what is decorators ? 
```bash 
Decorators allow us to wrap another function in order to extend the behaviour of the wrapped function,
without permanently modifying it.

def lower(str):
    return str

def Upper(func):
    
    def upper_case(str):
        return str.upper()
    return upper_case

lower = Upper(lower)

print(lower('My Name Khan'))


def decorator_lowercase(function):   # defining a Python decorator
    def wrapper():
        result = function()
        result_lowercase = result.lower()
        return result_lowercase
    return wrapper
    
@decorator_lowercase ## calling the decorator
def intro():                     # Normal function
    return 'Hello, I AM SAM'

print(intro())
```

#### Q-17 whats is task scheduler in python ?
```bash 
provides an easy way of scheduling the execution of certain tasks at specific times

pip install scheduler

import webbrowser

def open_gmail():
    url = 'https://mail.google.com'
    webbrowser.open(url)

import schedule
import time

schedule.every().day.at("10:00").do(open_gmail)

while True:
    schedule.run_pending()_init_()
    time.sleep(1)
```

#### Q-18 What is the purpose of _init_() function in Python?
```bash 
It acts as a constructor which gets executed when an object of a class is instantiated and allows the 
class to classify its attributes.
```

#### Q-19 What is the significance of the ‘self’ parameter in an object method? 
#### Should we always name this parameter as ‘self’?
```bash 
Parameter ‘self’ is used to refer to the object properties of a class. ‘self’ parameter is supposed
to be prefixed to the class object properties.
```

#### Q-20 What are membership operators in Python?
```bash 
in: If the value is found in a sequence, then the result will be true else false.
not in: If the value is not found in a sequence, then the result will be true else false.
```
