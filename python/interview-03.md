#### Q-1 What are python modules? Name some commonly used built-in modules in Python?
```bash
os
sys
math
random
data time
JSON
```

#### Q-2 Is Python a compiled language or an interpreted language?
```bash
Actually, Python is a partially compiled language and partially interpreted language. The compilation part is done first when we execute our code and this will generate byte code internally this byte code gets converted by the Python virtual machine(p.v.m) according to the underlying platform(machine+operating system).    
```

#### Q-3 What are Access Specifiers in Python?
```bash
Python uses the ‘_’ symbol to determine the access control for a specific data member or a member function of a class.

Public Access Modifier: The members of a class that are declared public are easily accessible from any part of the 
program. All data members and member functions of a class are public by default. 

Protected Access Modifier: The members of a class that are declared protected are only accessible to a class
derived from it. All data members of a class are declared protected by adding a single underscore ‘_’ symbol 
before the data members of that class. 

Private Access Modifier: The members of a class that are declared private are accessible within the class only, 
the private access modifier is the most secure access modifier. Data members of a class are declared private by
adding a double underscore ‘__’ symbol before the data member of that class. 
```

#### Q-4 What is Walrus Operator ?
```bash
The Walrus Operator allows you to assign a value to a variable within an expression. This can be useful 
when you need to use a value multiple times in a loop, but don’t want to repeat the calculation.

The Walrus Operator is represented by the `:=` syntax and can be used in a variety of contexts including while 
loops and if statements.

Note: Python versions before 3.8 doesn’t support Walrus Operator.

names = ["Jacob", "Joe", "Jim"]
 
if (name := input("Enter a name: ")) in names:
    print(f"Hello, {name}!")
else:
    print("Name not found.")   
```

#### Q-5 What is __init__ in Python?
```bash
In Python classes, the reserved method init serves a similar purpose as constructors in object-oriented 
programming (OOP) terminology. When a new object is created, the init method is automatically called, initializing
the object and allocating memory for it. This method can also be utilized to set initial values for variables.

class Human:
    def __init__(self, age):
        self.age = age
    def say(self):
        print('Hello, my age is', self.age)
h = Human(22)
h.say()
```

#### Q-6 How Would You Remove All Leading Whitespace in a String ?
```bash
“      Python”.lstrip
```

#### Q-7 What Is the Difference Between Del and Remove() on Lists ?
```bash
del : del removes all elements of a list within a given range 
Syntax: del list[start:end]

remove() : remove() removes the first occurrence of a particular character 
Syntax: list.remove(element)
```

#### Q-8 what is Monkey Patching in python ?  
```bash
the term monkey patch refers to dynamic (or run-time) modifications of a class or module. In Python, 
we can actually change the behavior of code at run-time.

class Greeting:
    def greet(self):
        return 'well Come'

def new_greet(self):
    return 'Hello well come to python'

Greeting.greet = new_greet
g = Greeting()
print(g.greet())
```

#### Q-9 How will you check if a class is a child of another class ?
```bash
This is done by using a method called issubclass() provided by python.

class Parent(object):
   pass   
 
class Child(Parent):
   pass   
 
# Driver Code
print(issubclass(Child, Parent))    #True
print(issubclass(Parent, Child))    #False
```

#### Q-11 What are Dict and List comprehensions?
```bash
x=[i for i in range(5)]
[0,1,2,3,4]

x=[i : i+2 for i in range(5)]
[0: 2, 1: 3, 2: 4, 3: 5, 4: 6]
```

#### Q-12 What is the difference between .py and .pyc files?
```bash
The .py files are the python source code files. While the .pyc files contain the bytecode of the python files. 
```

#### Q-13 what is inner function and closuser
```bash
# Python program to illustrate 
# closures 
def outerFunction(text): 
 
    def innerFunction(): 
        print(text) 
 
    # Note we are returning function
    # WITHOUT parenthesis
    return innerFunction  
 
if __name__ == '__main__': 
    myFunction = outerFunction('Hey!') 
    myFunction() 

closures in Python help to invoke functions outside their scope. The function innerFunction has its scope only inside the outerFunction. But with the use of Python closures, we can easily extend its scope to invoke a function outside its scope.

We may have variables in the global scope that are not used by many functions at times. Instead of defining variables in global scope, consider using a closure. They can be defined in the outer function and used in the inner function. Python Closures are also useful for avoiding the use of a global scope.

```

#### Q-14 SOLID priciple ?
```bash

Advantages : 

- Avoid duplicate
- easy to maintain
- easy to understand
- flexible software
- reduce complecity

S - Single responsibiity principle 
A class should have only one job. 
If a class has more than one responsibility, it becomes coupled. 
A change to one responsibility results to modification of the other responsibility.
```

#### Q-15 what is shallow copy and deep copy in python ?
```bash
A shallow copy constructs a new compound object and then (to the extent possible) inserts references into it to 
the objects found in the original. A deep copy constructs a new compound object and then, recursively, 
inserts copies into it of the objects found in the original.
```

#### Q-16 id() function in Python ?
```bash
id() function is a built-in function that returns the unique identifier of an object. The identifier is an integer, 
which represents the memory address of the object.
```

#### Q-17 can we change the order of dictionary in python ? 
```bash
No, the contents of a dictionary cannot be sorted in place like that of a list. However, we can indirectly sort the keys and values of a dictionary by using sorted() function: sorted(dictionary. keys())
```

#### Q-18 can we change the key in dictionary python ? 
```bash
Since keys are what dictionaries use to lookup values, you can't really change them. 
```

#### Q-19 what are the criteria to select key of dictionary python ?
```bash
 a dictionary key must be of a type that is immutable. For example, you can use an integer, float, string, 
 or Boolean as a dictionary key. However, neither a list nor another dictionary can serve as a dictionary key,
because lists and dictionaries are mutable.
```

#### Q-20 what is __new__ function in python
```bash
The __new__() is a static method of the object class. When you create a new object by calling the class, 
Python calls the __new__() method to create the object first and then calls the __init__() method to initialize 
the object's attributes.
```
