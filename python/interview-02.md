#### Q-1 What do you mean by ‘suites’ in Python ?
```bash
If expression
Suite
Else
Suite
```

#### Q-2 Difference Between Modules and Packages in Python ?
```bash
Module
The module is a simple Python file that contains collections of functions and global variables and 
with having a .py extension file.
import my_module

Package
The package is a simple directory having collections of modules. This directory contains Python 
modules and also having __init__.py file by which the interpreter interprets it as a Package.
from my_package.abc import a
```

#### Q-3 How Exception Handled In Python ?
```bash
Try: This block will test the exceptional error to occur.

Except: Here you can handle the error.

Else: If there is no exception then this block will be executed.

Finally: Finally block always gets executed either exception is generated or not.

try:
      # Some Code....!

except:
      # Optional Block
      # Handling of exception (if required)

else:
      # Some code .....
      # execute if no exception

finally:
      # Some code .....(always executed)
```

#### Q-4 How to use F String and Format or Replacement Operator ?
```bash
name = 'Kaushal'
role = 'Python Developer'
print(f"Hello, My name is {name} and I'm {role}")
print(("Hello, My name is {} and I'm {}").format(name,role))
```

#### Q-5 Does Python Support Multiple Inheritance. (Diamond Problem) ?
```bash 

class A:
	def abc(self):
		print("a")

class B(A):
	def abc(self):
		print("b")

class C(A):
	def abc(self):
		print("c")

class D(B,C):
	pass

d = D()
d.abc()

Output:
b
```

#### Q-6 How to initialize Empty List, Tuple, Dict and Set? 
```bash 
Empty List:
a = []

Empty Tuple:
a = ()

Empty Dict:
a = {}

Empty Set:
a = set()

```

#### Q-7 How Slicing Works In String Manipulation. Explain.
```bash 
Syntax: Str_Object[Start_Position:End_Position:Step]

Indexing
print(s[:])  #HelloWorld
print(s[::])  #HelloWorld
print(s[:5])  #Hello
print(s[2:5])  #llo
print(s[2:8:2])  #loo
print(s[8:1:-1])  #lroWoll
print(s[-4:-2])  #or
print(s[::-1])  #dlroWolleH
```

#### Q-8  What Is _a, __a,  __a__ in Python?
```bash
__a : Python doesn't have real private methods, so one underline in the beginning of a 
variable/function/method name means it's a private variable/function/method and It is for
internal use only

_a : Main purpose for _ is to use variable/method in class only If you want to use it outside 
of the class you can make public api.

__a__ : Name with start with __ and ends with same considers special methods in Python. 
```

#### Q-9 Difference Between Anonymous and Lambda Function
```bash
Anonymous function:
In Python, Anonymous function is a function that is defined without a name.
While normal functions are defined using the def keyword, Anonymous functions are defined using the lambda keyword.
Hence, anonymous functions are also called lambda functions.

Lambda function:
It can have any number of arguments but only one expression. 
The expression is evaluated and returned. 
Lambda functions can be used wherever function objects are required.
```

#### Q-10 Explain Append() And Extend() Property Of List ? 
```bash 
Append():
append() adds its argument as a single element to the end of a list. 
The length of the list itself will increase by one.

Extend():
extend() concatenates the first list with another list/iterable.
extend() iterates over its argument adding each element to the list, extending the list.

Consider 2 Lists - List1 & List2


list1 = [1,2,3]
list2 = [5,6,7]

Append():.

list1.append('AB')
print(list1)

Output:
[1, 2, 3, 'AB’]

Extend():.


list1.extend(‘AB’)
print(list1)

Output:
[1, 2, 3, ‘A’, ‘B’]

Append():.

list1.append(list2)
print(list1)

Output:
[1, 2, 3, [5, 6, 7]]

Extend():.


list1.extend(list2)
print(list1)

Output:
[1, 2, 3, 5, 6, 7]
```

#### Q-11 Why Python Is Called As Dynamic Typed Programming Language OR What Is Duck Typing?
```bash
The "Duck typing" name comes from the phrase, “If it walks like a duck and it quacks like a duck, 
then it must be a duck.” 

Python don't have any problem even if we don't declare the type of variable. 
It states the kind of variable in the runtime of the program. 
```

#### Q-12 What Is MRO In Python
```bash
In this case, the MRO would be C -> B -> A.
Since B was mentioned first in class declaration, it will be searched first while resolving a method.
MRO stands for Method Resolution Order
In Python, the MRO is from bottom to top and left to right.
```

#### Q-13 Which command is used to delete files in Python ?
```bash
import OS
OS.remove("abc.txt")
```

#### Q-14 What is the difference between deep copy and shallow copy?
```bash 
shallow copy creates a copy of the object but reference each elelment of the object
deep copy creates a copy of the object and element of the object
```

#### Q-15 How the string does get converted to a number?
```bash 
There is function eval() that can be used to convert a string into number but it is a bit 
slower and present many security risks
```

#### Q-16  What's the best way to get a list of all the keys in a dictionary?
```bash 
dict = {1:a, 2:b, 3:c} dict.keys() 
```

#### Q-17 What are the new features added in Python 3.9.0.0 version?
```bash
New Dictionary functions Merge(|) and Update(|=)
New String Methods to Remove Prefixes and Suffixes
```

#### Q-18 What is functional programming? Does Python follow a functional programming style? If yes, 
#### list a few methods to implement functionally oriented programming in Python.
```bash 
Functional programming is a coding style where the main source of logic in a program comes from functions.

Incorporating functional programming in our codes means writing pure functions.
```

#### Q-19 What do NumPy and SciPy have in common ?
```bash
SciPy stands for Scientific Python, while NumPy stands for Numerical Python. NumPy is the basic library for defining arrays and solving elementary mathematical issues, whereas SciPy is used for more sophisticated problems like numerical integration, optimization, and machine learning. 
```

#### Q-20 How to use Map, Filter and Reduce Function in Python?
```bash
map(fun, iter)
```