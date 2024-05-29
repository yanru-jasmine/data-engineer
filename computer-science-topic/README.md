# File I/O
## txt
File I/O is the ability of a program to take a file as input or create a file as output.
### open
automate the opening of a file
```python
name = input("What's your name? ")

file = open("names.txt", "a")
file.write(f"{name}\n")
file.close()
```

### with
automate the closing of a file
```python
name = input("What's your name? ")

with open("names.txt", "a") as file:
    file.write(f"{name}\n")
```
## csv
### read
```python
import csv

students = []

with open("students.csv") as file:
    reader = csv.DictReader(file)
    for row in reader:
        students.append({"name": row["name"], "home": row["home"]})

for student in sorted(students, key=lambda student: student["name"]):
    print(f"{student['name']} is in {student['home']}")
```
### write
```python
import csv

name = input("What's your name? ")
home = input("Where's your home? ")

with open("students.csv", "a") as file:
    writer = csv.DictWriter(file, fieldnames=["name", "home"])
    writer.writerow({"name": name, "home": home})
```

## PIL for image (binary file)
```python
# create animated gif
import sys
from PIL import Image

images = []

# append the second image to the first image
for arg in sys.argv[1:]:
    image = Image.open(arg)
    images.append(image)

# save the animated gif as costumes.gif
images[0].save(
    "costumes.gif", save_all=True, append_images=[images[1]], duration=200, loop=0

)


```



# Program paradigms
- Imperative – code directly controls execution flow and state change
    - procedural – organized as procedures that call each other
    - object-oriented – organized as objects that contain both data structure and associated behavior
        
- Declarative – code declares properties of the desired result, but not how to compute it
    - functional – a desired result is declared as the value of a series of function evaluations
    - logic – a desired result is declared as the answer to a question about a system of facts and rules
    - reactive – a desired result is declared with data streams and the propagation of change

 ## OOP (object-oriented programming)
 Python is an object oriented programming language, though we began with procedural programming.
 ```python
# Classes are a way by which, in object-oriented programming, we can create our own type of data and give them names.
# Convention: Class name is capitalized
# a class is an object or an instance
class Student:

    # Instance Methods:
    # __init__ method in Python is used to initialize objects of a class. It is also called a constructor.
    def __init__(self, name, house, patronus=None):

        # use raise to create exceptions that alerts a potential error created by the user 
        if not name:
            raise ValueError("Missing name")
        self.name = name
        self.house = house
        self.patronus = patronus

    # def __str__(self) provides a means by which a student is returned when called.
    def __str__(self):
        return f"{self.name} from {self.house}"

    # Decoractors:
    # use @property above a function to define house as a property of our class
    # by which we can define how attribute of our class (_house) should be set and retrieved
    # Getter for house
    @property
    def house(self):
        return self._house

    # Setter for house
    @house.setter
    def house(self, house):
        if house not in ["Gryffindor", "Hufflepuff", "Ravenclaw", "Slytherin"]:
            raise ValueError("Invalid house")
        self._house = house        # house is a property, while _house is an attribute  ("_" indicates users should not modify this value directly, should only be set through the house setter)

    def charm(self):
        match self.patronus:
            case "Stag":
                return "🐴"
            case "Otter":
                return "🦦"
            case "Jack Russell terrier":
                return "🐶"
            case _:
                return "🪄"


def main():
    student = get_student()
    print("Expecto Patronum!")
    print(student.charm())


def get_student():
    name = input("Name: ")
    house = input("House: ")
    patronus = input("Patronus: ") or None
    return Student(name, house, patronus)


if __name__ == "__main__":
    main()
```

## Class Methods

```python
class Student:
    def __init__(self, name, house):
        self.name = name
        self.house = house

    def __str__(self):
        return f"{self.name} from {self.house}"

    @classmethod
    def get(cls):
        name = input("Name: ")
        house = input("House: ")
        return cls(name, house)

def main():
    student = Student.get()
    print(student)


if __name__ == "__main__":
    main()
```

## Static Methods

## Inheritance
create a class that “inherits” methods, variables, and attributes from another class.
```python
class Wizard:
    def __init__(self, name):
        if not name:
            raise ValueError("Missing name")
        self.name = name

    ...


class Student(Wizard):
    def __init__(self, name, house):
        super().__init__(name)
        self.house = house

    ...


class Professor(Wizard):
    def __init__(self, name, subject):
        super().__init__(name)
        self.subject = subject

    ...


wizard = Wizard("Albus")
student = Student("Harry", "Gryffindor")
professor = Professor("Severus", "Defense Against the Dark Arts")
...
```

## global variables

Utilizing our powers from our experience with object-oriented programming, we can modify our code to use a class instead of a global variable through:
def __init__(self):
        self._balance = 0

```python
balance = 0

def main():
    print("Balance:", balance)
    deposit(100)
    withdraw(50)
    print("Balance:", balance)

def deposit(n):
    global balance
    balance += n

def withdraw(n):
    global balance
    balance -= n

if __name__ == "__main__":
    main()
```

# unpacking for print
## index
## total + * for list
```python
def total(galleons, sickles, knuts):
    return (galleons * 17 + sickles) * 29 + knuts

coins = [100, 50, 25]

print(total(*coins), "Knuts")
```
## total + ** for dictionary
```python
def total(galleons, sickles, knuts):
    return (galleons * 17 + sickles) * 29 + knuts

coins = {"galleons": 100, "sickles": 50, "knuts": 25}

print(total(**coins), "Knuts")
```

# args vs. kwargs
args is positional arguments, while kwargs is named / keywords arguments
## args
```python
def f(*args, **kwargs):
    print("Positional:", args)
f(100, 50, 25)
```
return `Positional: (100, 50, 25)`

##kwargs
```python
def f(*args, **kwargs):
    print("Named:", kwargs)
f(galleons=100, sickles=50, knuts=25)
```
return `Named: {'galleons': 100, 'sickles': 50, 'knuts': 25}`

# Modify List
List comprehension >  map
map may be microscopically faster in some cases (when you're not making a lambda for the purpose, but using the same function in map and a list comprehension). 
List comprehensions may be faster in other cases and most (not all) Pythonistas consider them more direct and clearer.
## map
`map` allows you to map a function to a sequence of values which has two arguments
- First, it takes a function we want applied to every element of a list. 
- Second, it takes that list itself
```python
def main():
    yell("This", "is", "CS50")

def yell(*words):
    uppercased = map(str.upper, words) # instead of using for loop
    print(*uppercased)

if __name__ == "__main__":
    main()
```

## List Comprehension
```python
def main():
    yell("This", "is", "CS50")

def yell(*words):
    uppercased = [arg.upper() for arg in words]
    print(*uppercased)

if __name__ == "__main__":
    main()
```

# Generator and Iterator
`print` created a list of value, while `yield` created an iterable object

# Compile
1. preprocessing: convert #inclue lines to the underlying prototypes
2. compiling: convert c into another language (assembly)
3. assembling: convert assembly code to binary code
4. linking: combine binary codes into one final file

# Reverse Engineering
convert machine code back to source code

# Memory
- bool    1 byte
- int     4 bytes
- long    8 bytes
- float   4 bytes
- double  8 bytes
- char    1 byte
- string

# Array
continuous

# Cryptography
encryption: scramble the info so that only you and the recipient can receive it

plaintext (message written in human language) + key -> |  cipher (an algorithm for encrypting or scrambling info in a reversible way)  |  ->  ciphertext

# Algorithms
## Linear Search
search from left to right or right to left 
## Binary Search
search from the middle
## running time (efficiency of algorithm)
time to solve vs. size of problem
O(n) O(n/2) -> functionally same
O(log n)

common Big O:
- O(n^2): shake every one's hand in the room
- O(n*log n): 
- O(n): linear search
- O(log n): binary search
- O(1): constant steps (everyone stands up at the same time)
