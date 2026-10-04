# 🐍 Python Object-Oriented Programming (OOP) Mastery

A complete, interview-focused, hands-on guide to **Object-Oriented Programming in Python**, starting from absolute fundamentals and progressing to advanced Python internals, design patterns, metaprogramming, and real-world projects.

This README is designed for:

* 🎓 Computer Engineering / CS students
* 💼 Python developer interviews
* 🤖 AI/ML and Data Science engineers
* 🧑‍💻 Backend developers
* 🚀 Freshers preparing for off-campus placements
* 📚 Anyone who wants strong Python OOP fundamentals

---

# 📚 Table of Contents

## Module 0 — OOP Theory & Fundamentals

1. [What is OOP?](#1-what-is-oop)
2. [Why Do We Need OOP?](#2-why-do-we-need-oop)
3. [Procedural vs OOP](#3-procedural-vs-oop)
4. [Class](#4-class)
5. [Object](#5-object)
6. [Class vs Object](#6-class-vs-object)
7. [Attributes and Methods](#7-attributes-and-methods)
8. [`self`](#8-self)
9. [`__init__()`](#9-__init__)
10. [Instance Variables](#10-instance-variables)
11. [Class Variables](#11-class-variables)
12. [Instance Methods](#12-instance-methods)
13. [Class Methods](#13-class-methods)
14. [Static Methods](#14-static-methods)
15. [Four Pillars of OOP](#15-four-pillars-of-oop)
16. [Encapsulation](#16-encapsulation)
17. [Abstraction](#17-abstraction)
18. [Inheritance](#18-inheritance)
19. [Polymorphism](#19-polymorphism)
20. [Composition](#20-composition)
21. [Association, Aggregation and Composition](#21-association-aggregation-and-composition)
22. [Access Conventions](#22-access-conventions)
23. [`@property`](#23-property)
24. [`super()`](#24-super)
25. [Method Overriding](#25-method-overriding)
26. [Method Overloading](#26-method-overloading)
27. [Duck Typing](#27-duck-typing)
28. [Dynamic Binding](#28-dynamic-binding)
29. [Object Lifecycle](#29-object-lifecycle)
30. [`__new__()` vs `__init__()`](#30-__new__-vs-__init__)

## Module 1 — Core Foundations

* Lab 01 — Classes & Objects
* Lab 02 — Instance Methods
* Lab 03 — Class vs Instance Variables
* Lab 04 — Class Methods
* Lab 05 — Static Methods

## Module 2 — Intermediate OOP

* Lab 06 — Encapsulation
* Lab 07 — Properties
* Lab 08 — Inheritance
* Lab 09 — MRO
* Lab 10 — Polymorphism & Duck Typing

## Module 3 — Advanced OOP

* Lab 11 — Operator Overloading
* Lab 12 — Custom Containers
* Lab 13 — Context Managers
* Lab 14 — Abstract Base Classes
* Lab 15 — Callable Objects

## Module 4 — Design Patterns & Metaprogramming

* Lab 16 — Singleton Pattern
* Lab 17 — Factory Pattern
* Lab 18 — Method Decorators
* Lab 19 — Descriptors
* Lab 20 — Metaclasses

## Mini Projects

1. Bank Account Management System
2. Library & Book Reservation System
3. Terminal RPG Engine
4. Lightweight ORM Engine
5. Event-Driven Task Scheduler

## Interview Preparation

* 80 Frequently Asked Python OOP Interview Questions
* Quick Revision Sheet
* Interview Preparation Checklist

---

# 🎯 Learning Objectives

After completing this course, you should be able to:

* Understand OOP from first principles
* Create classes and objects
* Design reusable Python classes
* Understand instance and class state
* Use instance, class and static methods
* Implement encapsulation
* Implement abstraction using ABCs
* Use inheritance correctly
* Understand multiple inheritance
* Explain and use MRO
* Implement polymorphism
* Understand duck typing
* Use composition
* Implement operator overloading
* Understand dunder methods
* Build custom iterables and containers
* Create context managers
* Build abstract classes
* Use descriptors
* Understand metaclasses
* Implement common design patterns
* Explain OOP concepts confidently in interviews
* Design real-world applications using OOP principles

---

# 🧠 MODULE 0 — OOP THEORY & FUNDAMENTALS

# 1. What is OOP?

**Object-Oriented Programming (OOP)** is a programming paradigm where software is designed around **objects**.

An object contains:

```text
Data + Behavior
```

For example, consider a bank account.

### Data

```text
account_number
owner
balance
```

### Behavior

```text
deposit()
withdraw()
check_balance()
```

Instead of keeping these separately, OOP combines them into one object.

```python
class BankAccount:

    def __init__(self, owner, balance):
        self.owner = owner
        self.balance = balance

    def deposit(self, amount):
        self.balance += amount

    def withdraw(self, amount):
        self.balance -= amount
```

Create an object:

```python
account = BankAccount("Sandesh", 10000)
```

Now:

```python
account.deposit(2000)
account.withdraw(1000)
```

The object contains both the data and operations that work on that data.

---

# 2. Why Do We Need OOP?

Imagine building a large application without OOP.

You may have:

```python
student_name
student_age
student_marks

teacher_name
teacher_age
teacher_subject
```

As the application grows, managing everything becomes difficult.

OOP allows us to model real-world entities:

```text
Student
Teacher
Course
Employee
BankAccount
Vehicle
Product
Order
Payment
```

Each entity can become a class.

### Main advantages

* Reusability
* Maintainability
* Modularity
* Encapsulation
* Abstraction
* Extensibility
* Easier testing
* Better organization

---

# 3. Procedural vs OOP

## Procedural Programming

The program is organized around functions.

```python
balance = 1000

def deposit(balance, amount):
    return balance + amount

balance = deposit(balance, 500)
```

## Object-Oriented Programming

The data and behavior are grouped together.

```python
class BankAccount:

    def __init__(self, balance):
        self.balance = balance

    def deposit(self, amount):
        self.balance += amount
```

### Comparison

| Procedural                           | OOP                                           |
| ------------------------------------ | --------------------------------------------- |
| Function-centered                    | Object-centered                               |
| Data and functions often separate    | Data + behavior combined                      |
| Good for smaller programs            | Good for larger systems                       |
| Less emphasis on state encapsulation | Strong encapsulation                          |
| Reuse through functions              | Reuse through classes/inheritance/composition |

---

# 4. Class

A **class is a blueprint/template for creating objects**.

Example:

```python
class Student:
    pass
```

Create objects:

```python
s1 = Student()
s2 = Student()
```

Here:

```text
Student → Class
s1      → Object
s2      → Object
```

---

# 5. Object

An **object is an instance of a class**.

```python
class Car:
    pass

car1 = Car()
car2 = Car()
```

`car1` and `car2` are separate objects created from `Car`.

---

# 6. Class vs Object

| Class                                 | Object                |
| ------------------------------------- | --------------------- |
| Blueprint                             | Actual instance       |
| Logical definition                    | Real entity           |
| Doesn't represent one specific entity | Represents one entity |
| Defines attributes/methods            | Contains actual state |
| `Student`                             | `student1`            |

Example:

```python
class Student:
    pass

student1 = Student()
student2 = Student()
```

---

# 7. Attributes and Methods

A class usually contains:

```text
Attributes → Data
Methods    → Behavior
```

Example:

```python
class Student:

    def __init__(self, name, marks):
        self.name = name
        self.marks = marks

    def display(self):
        print(self.name)
        print(self.marks)
```

Here:

```text
name  → attribute
marks → attribute
display() → method
```

---

# 8. `self`

`self` refers to the **current object**.

```python
class Student:

    def __init__(self, name):
        self.name = name

    def display(self):
        print(self.name)
```

When:

```python
s1 = Student("Sandesh")
s1.display()
```

Python internally passes the object:

```python
Student.display(s1)
```

Therefore:

```python
self.name
```

means:

> "The `name` belonging to this particular object."

---

# 9. `__init__()`

`__init__()` initializes an object after it has been created.

```python
class Student:

    def __init__(self, name, age):
        self.name = name
        self.age = age
```

When:

```python
student = Student("Rahul", 21)
```

Python initializes the object using:

```python
__init__(student, "Rahul", 21)
```

Important:

> `__init__()` is an initializer, not the method responsible for allocating the object.

---

# 10. Instance Variables

Instance variables belong to individual objects.

```python
class Student:

    def __init__(self, name):
        self.name = name
```

```python
s1 = Student("A")
s2 = Student("B")
```

Memory/state conceptually:

```text
s1 → name = A
s2 → name = B
```

Changing `s1.name` does not normally change `s2.name`.

---

# 11. Class Variables

Class variables belong to the class and are shared unless an instance shadows them.

```python
class Employee:

    company = "Tech Corp"

    def __init__(self, name):
        self.name = name
```

```python
e1 = Employee("A")
e2 = Employee("B")

print(e1.company)
print(e2.company)
```

Both can access:

```text
Tech Corp
```

A common use case is tracking shared information.

```python
class Employee:

    employee_count = 0

    def __init__(self, name):
        self.name = name
        Employee.employee_count += 1
```

---

# 12. Instance Methods

Instance methods operate on a particular object.

They receive:

```python
self
```

Example:

```python
class BankAccount:

    def deposit(self, amount):
        self.balance += amount
```

---

# 13. Class Methods

A class method receives:

```python
cls
```

Use:

```python
@classmethod
```

Example:

```python
class Employee:

    company = "Tech Corp"

    @classmethod
    def change_company(cls, name):
        cls.company = name
```

Call:

```python
Employee.change_company("Google")
```

### Common use

Alternative constructors.

```python
class Date:

    def __init__(self, day, month, year):
        self.day = day
        self.month = month
        self.year = year

    @classmethod
    def from_string(cls, value):
        day, month, year = map(int, value.split("-"))
        return cls(day, month, year)
```

Usage:

```python
date = Date.from_string("25-12-2024")
```

---

# 14. Static Methods

A static method does not receive `self` or `cls`.

```python
class MathUtils:

    @staticmethod
    def is_even(number):
        return number % 2 == 0
```

Usage:

```python
MathUtils.is_even(10)
```

Use static methods for logically related utility operations that don't need object/class state.

---

# 15. Four Pillars of OOP

The four commonly discussed pillars are:

```text
        OOP
         |
  ----------------
  |      |       |
Encap  Abstr   Inherit
         |
     Polymorphism
```

More clearly:

1. Encapsulation
2. Abstraction
3. Inheritance
4. Polymorphism

---

# 16. Encapsulation

Encapsulation means **bundling data and methods together while controlling access to internal state**.

Example:

```python
class BankAccount:

    def __init__(self, balance):
        self.__balance = balance

    def deposit(self, amount):
        if amount > 0:
            self.__balance += amount

    def get_balance(self):
        return self.__balance
```

The internal balance is not intended to be directly modified.

```python
account = BankAccount(1000)

account.deposit(500)

print(account.get_balance())
```

---

# 17. Access Conventions in Python

Python does not enforce Java-style `private`/`protected` access modifiers in the same way.

## Public

```python
self.name
```

Accessible normally.

## Protected convention

```python
self._name
```

A single underscore means:

> "This is intended for internal/subclass use."

It is a convention, not strict enforcement.

## Private / Name Mangling

```python
self.__password
```

Python name-mangles it approximately to:

```text
_ClassName__password
```

Example:

```python
class User:

    def __init__(self):
        self.__password = "secret"
```

---

# 18. Abstraction

Abstraction means exposing the required interface while hiding implementation details.

Example:

```python
from abc import ABC, abstractmethod

class PaymentProcessor(ABC):

    @abstractmethod
    def pay(self, amount):
        pass
```

Concrete implementation:

```python
class StripeProcessor(PaymentProcessor):

    def pay(self, amount):
        print(f"Paid {amount} using Stripe")
```

The user knows:

```python
processor.pay(100)
```

They don't need to know the internal payment-processing implementation.

---

# 19. Inheritance

Inheritance allows a class to derive behavior from another class.

```python
class Vehicle:

    def drive(self):
        print("Vehicle is driving")


class Car(Vehicle):
    pass
```

Now:

```python
car = Car()
car.drive()
```

The child class inherits `drive()`.

---

# 20. Types of Inheritance

## Single inheritance

```text
A
|
B
```

```python
class B(A):
    pass
```

## Multilevel inheritance

```text
A
|
B
|
C
```

## Hierarchical inheritance

```text
     A
   /   \
  B     C
```

## Multiple inheritance

```text
A     B
 \   /
   C
```

```python
class C(A, B):
    pass
```

## Hybrid inheritance

Combination of multiple inheritance structures.

---

# 21. `super()`

`super()` is commonly used to access behavior from a parent class according to Python's method resolution mechanism.

```python
class Vehicle:

    def __init__(self, brand):
        self.brand = brand


class Car(Vehicle):

    def __init__(self, brand, model):
        super().__init__(brand)
        self.model = model
```

Without `super()`:

```python
self.brand = brand
```

would have to be repeated.

---

# 22. Method Overriding

A child class can provide its own implementation of a parent method.

```python
class Animal:

    def sound(self):
        print("Some sound")


class Dog(Animal):

    def sound(self):
        print("Bark")
```

```python
dog = Dog()
dog.sound()
```

Output:

```text
Bark
```

---

# 23. Method Overloading

Traditional method overloading with multiple methods of the same name and different signatures is not directly supported like Java/C++.

This does **not** create two overloads:

```python
class Calculator:

    def add(self, a):
        pass

    def add(self, a, b):
        pass
```

The second definition replaces the first.

Python can achieve similar behavior using:

* Default arguments
* `*args`
* `**kwargs`
* Type checking

Example:

```python
class Calculator:

    def add(self, *numbers):
        return sum(numbers)
```

---

# 24. Polymorphism

Polymorphism means:

> One interface, different implementations.

Example:

```python
class Dog:

    def speak(self):
        return "Bark"


class Cat:

    def speak(self):
        return "Meow"
```

```python
animals = [Dog(), Cat()]

for animal in animals:
    print(animal.speak())
```

Output:

```text
Bark
Meow
```

The same:

```python
animal.speak()
```

behaves differently depending on the object.

---

# 25. Duck Typing

Python strongly embraces duck typing.

> If an object provides the required behavior, its exact class may not matter.

```python
class PDF:

    def generate(self):
        return "PDF generated"


class CSV:

    def generate(self):
        return "CSV generated"
```

```python
def render(report):
    print(report.generate())
```

Both work:

```python
render(PDF())
render(CSV())
```

The function cares that the object has:

```python
generate()
```

---

# 26. Composition

Composition means building a class using objects of other classes.

Example:

```python
class Engine:

    def start(self):
        print("Engine started")


class Car:

    def __init__(self):
        self.engine = Engine()

    def start(self):
        self.engine.start()
```

Here:

```text
Car HAS-A Engine
```

Composition is often preferred when the relationship is:

```text
HAS-A
```

rather than:

```text
IS-A
```

---

# 27. Association, Aggregation and Composition

## Association

General relationship.

```text
Teacher ↔ Student
```

## Aggregation

Weak HAS-A relationship.

```text
Department → Teacher
```

The teacher may exist independently.

## Composition

Strong HAS-A relationship.

```text
House → Room
```

The room is conceptually part of the house.

---

# 28. `@property`

`@property` allows method-based logic to be accessed like an attribute.

```python
class Temperature:

    def __init__(self, celsius):
        self._celsius = celsius

    @property
    def celsius(self):
        return self._celsius
```

Usage:

```python
temperature.celsius
```

instead of:

```python
temperature.celsius()
```

A setter can validate values:

```python
@celsius.setter
def celsius(self, value):
    if value < -273.15:
        raise ValueError("Invalid temperature")

    self._celsius = value
```

---

# 29. Dynamic Binding

Python determines method behavior at runtime.

```python
class Dog:

    def sound(self):
        return "Bark"


class Cat:

    def sound(self):
        return "Meow"
```

```python
animal = Dog()
print(animal.sound())

animal = Cat()
print(animal.sound())
```

The actual object determines which implementation is executed.

---

# 30. `__new__()` vs `__init__()`

This is one of the most frequently asked Python interview questions.

## `__new__()`

Responsible for creating/returning a new instance.

## `__init__()`

Initializes an already-created instance.

Conceptually:

```text
Object creation
      ↓
   __new__()
      ↓
Object created
      ↓
   __init__()
      ↓
Object initialized
```

Example:

```python
class Student:

    def __new__(cls, name):
        print("Creating object")
        return super().__new__(cls)

    def __init__(self, name):
        print("Initializing object")
        self.name = name
```

---

# 🧪 MODULE 1 — CORE FOUNDATIONS

# Lab 01 — Defining Classes & Instantiating Objects

### Objective

Learn:

* Class creation
* Object creation
* Constructor
* Instance variables
* Instance methods

```python
class Car:

    def __init__(self, make, model, year):
        self.make = make
        self.model = model
        self.year = year

    def get_info(self):
        return f"{self.year} {self.make} {self.model}"


car1 = Car("Toyota", "Corolla", 2022)

print(car1.get_info())
```

Expected:

```text
2022 Toyota Corolla
```

---

# Lab 02 — Instance Methods & State Modification

```python
class BankAccount:

    def __init__(self, owner, balance=0):
        self.owner = owner
        self.balance = balance

    def deposit(self, amount):
        if amount <= 0:
            raise ValueError("Amount must be positive")

        self.balance += amount

    def withdraw(self, amount):
        if amount <= 0:
            raise ValueError("Amount must be positive")

        if amount > self.balance:
            raise ValueError("Insufficient funds")

        self.balance -= amount
```

---

# Lab 03 — Class Variables

```python
class Employee:

    company_name = "Tech Corp"
    employee_count = 0

    def __init__(self, name, role):
        self.name = name
        self.role = role

        Employee.employee_count += 1
```

---

# Lab 04 — Class Methods

```python
class Date:

    def __init__(self, day, month, year):
        self.day = day
        self.month = month
        self.year = year

    @classmethod
    def from_string(cls, date_string):
        day, month, year = map(int, date_string.split("-"))
        return cls(day, month, year)
```

Usage:

```python
date = Date.from_string("25-12-2024")
```

---

# Lab 05 — Static Methods

```python
class MathUtils:

    @staticmethod
    def is_prime(n):

        if n < 2:
            return False

        for i in range(2, int(n ** 0.5) + 1):

            if n % i == 0:
                return False

        return True
```

---

# 🔐 MODULE 2 — INTERMEDIATE OOP

# Lab 06 — Encapsulation

```python
class UserAccount:

    def __init__(self, username, email, password):
        self.username = username
        self._email = email
        self.__password = password

    def verify_password(self, password):
        return self.__password == password

    def update_password(self, old_password, new_password):

        if self.verify_password(old_password):
            self.__password = new_password
            return True

        return False
```

The uploaded source uses this same structure to demonstrate protected `_email` and private `__password`.

---

# Lab 07 — Properties

```python
class Temperature:

    def __init__(self, celsius=0):
        self._celsius = celsius

    @property
    def celsius(self):
        return self._celsius

    @celsius.setter
    def celsius(self, value):

        if value < -273.15:
            raise ValueError("Below absolute zero")

        self._celsius = value

    @property
    def fahrenheit(self):
        return self._celsius * 9 / 5 + 32
```

---

# Lab 08 — Inheritance

```python
class Vehicle:

    def __init__(self, brand, speed):
        self.brand = brand
        self.speed = speed

    def drive(self):
        return f"{self.brand} is traveling at {self.speed} km/h"


class ElectricCar(Vehicle):

    def __init__(self, brand, speed, battery_capacity):
        super().__init__(brand, speed)
        self.battery_capacity = battery_capacity

    def drive(self):
        return super().drive() + \
               f" Battery: {self.battery_capacity} kWh"
```

---

# Lab 09 — Method Resolution Order

Consider:

```text
       A
      / \
     B   C
      \ /
       D
```

```python
class A:

    def show(self):
        return "A"


class B(A):

    def show(self):
        return f"B -> {super().show()}"


class C(A):

    def show(self):
        return f"C -> {super().show()}"


class D(B, C):

    def show(self):
        return f"D -> {super().show()}"
```

```python
d = D()

print(d.show())
print(D.mro())
```

Expected method chain:

```text
D → B → C → A
```

Python uses C3 linearization for MRO.

---

# Lab 10 — Polymorphism & Duck Typing

```python
class PDFReport:

    def generate(self):
        return "PDF content"


class CSVReport:

    def generate(self):
        return "CSV content"


class HTMLReport:

    def generate(self):
        return "HTML content"


def render_report(report):
    print(report.generate())
```

```python
render_report(PDFReport())
render_report(CSVReport())
render_report(HTMLReport())
```

---

# ⚙️ MODULE 3 — ADVANCED OOP

# Lab 11 — Magic/Dunder Methods

Dunder means:

```text
Double UNDERscore
```

Examples:

```python
__init__
__str__
__repr__
__eq__
__add__
__len__
__getitem__
__call__
```

Example:

```python
class Vector:

    def __init__(self, x, y):
        self.x = x
        self.y = y

    def __add__(self, other):
        return Vector(
            self.x + other.x,
            self.y + other.y
        )

    def __eq__(self, other):
        return self.x == other.x and self.y == other.y

    def __repr__(self):
        return f"Vector({self.x}, {self.y})"
```

---

# Lab 12 — Custom Containers

```python
class Playlist:

    def __init__(self, name):
        self.name = name
        self._songs = []

    def add_song(self, song):
        self._songs.append(song)

    def __len__(self):
        return len(self._songs)

    def __getitem__(self, index):
        return self._songs[index]
```

Now:

```python
playlist = Playlist("Chill")

playlist.add_song("Song A")
playlist.add_song("Song B")

print(len(playlist))
print(playlist[0])
```

---

# Lab 13 — Context Managers

Python context managers implement:

```python
__enter__()
__exit__()
```

Example:

```python
class SafeFileWriter:

    def __init__(self, filepath):
        self.filepath = filepath
        self.file = None

    def __enter__(self):
        self.file = open(self.filepath, "w")
        return self.file

    def __exit__(self, exc_type, exc_value, traceback):
        self.file.close()
```

Usage:

```python
with SafeFileWriter("test.txt") as file:
    file.write("Hello")
```

---

# Lab 14 — Abstract Base Classes

```python
from abc import ABC, abstractmethod


class PaymentProcessor(ABC):

    @abstractmethod
    def pay(self, amount):
        pass


class StripeProcessor(PaymentProcessor):

    def pay(self, amount):
        print(f"Processing {amount} using Stripe")


class PayPalProcessor(PaymentProcessor):

    def pay(self, amount):
        print(f"Processing {amount} using PayPal")
```

---

# Lab 15 — Callable Objects

Implement:

```python
__call__()
```

to make an object callable.

```python
class Multiplier:

    def __init__(self, factor):
        self.factor = factor

    def __call__(self, value):
        return value * self.factor
```

Usage:

```python
double = Multiplier(2)

print(double(10))
```

Output:

```text
20
```

---

# 🏗️ MODULE 4 — DESIGN PATTERNS & METAPROGRAMMING

# Lab 16 — Singleton Pattern

A Singleton attempts to ensure that a class has one shared instance.

```python
class DatabaseConnection:

    _instance = None

    def __new__(cls):

        if cls._instance is None:
            cls._instance = super().__new__(cls)

        return cls._instance
```

Usage:

```python
db1 = DatabaseConnection()
db2 = DatabaseConnection()

print(db1 is db2)
```

---

# Lab 17 — Factory Pattern

The Factory pattern centralizes object creation.

```python
class EmailNotification:

    def send(self, message):
        print("Email:", message)


class SMSNotification:

    def send(self, message):
        print("SMS:", message)


class NotificationFactory:

    @staticmethod
    def create(channel):

        if channel == "email":
            return EmailNotification()

        if channel == "sms":
            return SMSNotification()

        raise ValueError("Unknown channel")
```

---

# Lab 18 — Decorators Inside Classes

```python
from functools import wraps
import time


def audit_log(func):

    @wraps(func)
    def wrapper(*args, **kwargs):

        start = time.time()

        result = func(*args, **kwargs)

        duration = time.time() - start

        print(
            f"{func.__name__} executed "
            f"in {duration:.6f}s"
        )

        return result

    return wrapper
```

Usage:

```python
class DataService:

    @audit_log
    def process_data(self, data):
        return [x * 2 for x in data]
```

---

# Lab 19 — Descriptors

A descriptor can control attribute access.

Main methods:

```python
__get__
__set__
__delete__
```

Example:

```python
class BoundedNumber:

    def __init__(self, minimum, maximum):
        self.minimum = minimum
        self.maximum = maximum

    def __set_name__(self, owner, name):
        self.private_name = "_" + name

    def __get__(self, instance, owner):

        if instance is None:
            return self

        return getattr(instance, self.private_name)

    def __set__(self, instance, value):

        if not self.minimum <= value <= self.maximum:
            raise ValueError("Value outside allowed range")

        setattr(instance, self.private_name, value)
```

---

# Lab 20 — Metaclasses

A metaclass is essentially a class whose instances are classes.

Python's default metaclass is commonly:

```python
type
```

Example:

```python
class MyMeta(type):

    def __new__(mcls, name, bases, attrs):

        print("Creating:", name)

        return super().__new__(
            mcls,
            name,
            bases,
            attrs
        )
```

Usage:

```python
class User(metaclass=MyMeta):
    pass
```

---

# 🛠️ MINI PROJECT 1 — BANK ACCOUNT MANAGEMENT

Concepts:

* Encapsulation
* ABC
* Properties
* Inheritance
* Context managers
* Transactions

```python
from abc import ABC, abstractmethod


class Account(ABC):

    def __init__(self, account_number, owner, balance=0):
        self.account_number = account_number
        self.owner = owner
        self._balance = balance

    @property
    def balance(self):
        return self._balance

    def deposit(self, amount):

        if amount <= 0:
            raise ValueError("Amount must be positive")

        self._balance += amount

    @abstractmethod
    def withdraw(self, amount):
        pass
```

---

# 🛠️ MINI PROJECT 2 — LIBRARY MANAGEMENT

Entities:

```text
Library
Book
Member
Reservation
```

Possible relationships:

```text
Library HAS-A Book
Member BORROWS Book
Member RESERVES Book
```

Key concepts:

* Composition
* Encapsulation
* Dunder methods
* Custom containers

---

# 🛠️ MINI PROJECT 3 — TERMINAL RPG

Classes:

```text
Character
    |
    ├── Warrior
    └── Mage
```

This demonstrates:

* Abstraction
* Inheritance
* Polymorphism
* Method overriding

---

# 🛠️ MINI PROJECT 4 — LIGHTWEIGHT ORM

Build:

```python
class User:
    name
    age
```

with descriptors that validate field types.

Example:

```python
class Field:

    def __init__(self, field_type):
        self.field_type = field_type

    def __set_name__(self, owner, name):
        self.name = name

    def __get__(self, instance, owner):

        if instance is None:
            return self

        return instance.__dict__.get(self.name)

    def __set__(self, instance, value):

        if not isinstance(value, self.field_type):
            raise TypeError("Invalid type")

        instance.__dict__[self.name] = value
```

---

# 🛠️ MINI PROJECT 5 — EVENT-DRIVEN TASK SCHEDULER

Concepts:

* Singleton
* Callable objects
* Functions as objects
* Collections
* Event/task execution

Example architecture:

```text
Scheduler
   |
   ├── Task 1
   ├── Task 2
   └── Task 3
```

---

# 💼 80 PYTHON OOP INTERVIEW QUESTIONS

## 🟢 Beginner

### 1. What is OOP?

OOP is a programming paradigm that organizes software around objects containing data and behavior.

### 2. What is a class?

A class is a blueprint for creating objects.

### 3. What is an object?

An object is an instance of a class.

### 4. Class vs object?

A class defines the structure; an object is a concrete instance.

### 5. What is `self`?

`self` refers to the current object instance.

### 6. What is `__init__()`?

It initializes an object after creation.

### 7. What is an instance variable?

A variable associated with a particular object.

### 8. What is a class variable?

A variable defined at class level and generally shared across instances.

### 9. What is an instance method?

A method that receives `self`.

### 10. What is a class method?

A method decorated with `@classmethod` that receives `cls`.

### 11. What is a static method?

A method that receives neither `self` nor `cls`.

### 12. Why use classes?

To organize related data and behavior into reusable units.

### 13. Can multiple objects be created from one class?

Yes.

### 14. What is object state?

The data stored by an object at a particular point in time.

### 15. What is object behavior?

The operations an object can perform through its methods.

---

# 🟡 Four Pillars

### 16. What is encapsulation?

Bundling data and behavior while controlling access to internal state.

### 17. How is encapsulation implemented in Python?

Using conventions such as `_name`, name mangling with `__name`, properties, and controlled methods.

### 18. Does Python have true private variables?

Python does not enforce private access in the same strict way as some languages. Double underscores trigger name mangling.

### 19. What is name mangling?

Python transforms names such as:

```python
__value
```

inside a class into a class-qualified form.

### 20. `_x` vs `__x`?

```text
_x  → protected/internal-use convention
__x → name mangling
```

### 21. What is abstraction?

Exposing essential behavior while hiding implementation details.

### 22. How do you implement abstraction?

Commonly using:

```python
ABC
@abstractmethod
```

### 23. What is inheritance?

A mechanism through which one class derives behavior from another.

### 24. What is polymorphism?

The ability to use a common interface with different implementations.

### 25. What is method overriding?

A child class provides its own implementation of an inherited method.

### 26. Does Python support method overloading?

Not traditional signature-based overloading in the same way as Java/C++. Python commonly uses defaults, `*args`, or other techniques.

### 27. Overloading vs overriding?

```text
Overloading → same conceptual operation with different arguments
Overriding  → child replaces inherited behavior
```

### 28. Abstraction vs encapsulation?

```text
Abstraction  → What should be exposed?
Encapsulation → How is internal state controlled?
```

### 29. What are the types of inheritance?

Common forms:

* Single
* Multiple
* Multilevel
* Hierarchical
* Hybrid

### 30. What is multiple inheritance?

A class inherits from more than one parent.

---

# 🟠 Intermediate

### 31. What is `super()`?

It provides a way to access inherited behavior according to Python's MRO.

### 32. What is MRO?

Method Resolution Order defines the order Python uses to search for attributes/methods through inheritance.

### 33. How do you inspect MRO?

```python
ClassName.mro()
```

or:

```python
ClassName.__mro__
```

### 34. What is C3 linearization?

The algorithm Python uses to calculate a consistent MRO for multiple inheritance.

### 35. What is duck typing?

Programming based on an object's supported behavior rather than requiring a particular explicit type.

### 36. What is dynamic binding?

The appropriate method implementation is determined at runtime.

### 37. What is composition?

Building an object from other objects.

### 38. Composition vs inheritance?

```text
Inheritance → IS-A
Composition → HAS-A
```

### 39. What is association?

A general relationship between objects.

### 40. What is aggregation?

A weaker whole-part relationship where the contained object can exist independently.

### 41. What is composition?

A stronger whole-part relationship where the component is conceptually owned by the containing object.

### 42. What is `@property`?

A decorator that allows method-based attribute access.

### 43. Why use properties?

For validation, controlled access, computed attributes, and maintaining a clean API.

### 44. What is operator overloading?

Giving operators such as `+`, `==`, and `<` custom behavior for user-defined objects.

### 45. What are dunder methods?

Special methods with names surrounded by double underscores.

### 46. What is `__str__()`?

Defines a user-friendly string representation.

### 47. What is `__repr__()`?

Defines a representation intended to be useful for debugging/development.

### 48. `__str__()` vs `__repr__()`?

```text
__str__  → user-friendly representation
__repr__ → developer/debug representation
```

### 49. What is `__eq__()`?

Defines equality behavior for objects.

### 50. What is `__add__()`?

Defines behavior for the `+` operator.

### 51. What is `__len__()`?

Defines behavior for `len(object)`.

### 52. What is `__getitem__()`?

Allows objects to support subscription/indexing such as:

```python
obj[0]
```

### 53. What is `__call__()`?

Makes an object callable:

```python
obj()
```

### 54. What is a context manager?

An object that manages setup and cleanup around a block, commonly used with `with`.

### 55. Which methods implement a context manager?

```python
__enter__()
__exit__()
```

### 56. What is an abstract base class?

A class used to define an interface/contract for subclasses.

---

# 🔴 Advanced

### 57. What is `__new__()`?

It participates in creating and returning a new instance.

### 58. `__new__()` vs `__init__()`?

```text
__new__  → creates/returns instance
__init__ → initializes instance
```

### 59. What is a descriptor?

An object defining attribute access behavior through methods such as:

```python
__get__
__set__
__delete__
```

### 60. Descriptor vs property?

`property` is a convenient built-in descriptor mechanism for individual attributes. Custom descriptors can encapsulate reusable attribute-management logic.

### 61. What is a metaclass?

A class whose instances are classes.

### 62. What is Python's default metaclass?

Generally:

```python
type
```

### 63. What is a custom metaclass?

A subclass of `type` that customizes class creation or behavior.

### 64. What is a decorator?

A callable that modifies or wraps another callable/class without necessarily changing its original source.

### 65. What is a callable object?

An object implementing:

```python
__call__()
```

### 66. What is Singleton?

A design pattern intended to provide a single shared instance.

### 67. How can Singleton be implemented?

One common technique uses:

```python
__new__()
```

### 68. What is Factory Pattern?

A pattern that centralizes or abstracts object creation.

### 69. What is dependency injection?

Providing dependencies to an object instead of making the object create them internally.

### 70. What is SOLID?

Five design principles:

```text
S → Single Responsibility
O → Open/Closed
L → Liskov Substitution
I → Interface Segregation
D → Dependency Inversion
```

### 71. What is Single Responsibility Principle?

A class should have one primary responsibility/reason to change.

### 72. What is Open/Closed Principle?

Software entities should generally be open for extension but closed for modification.

### 73. What is Liskov Substitution Principle?

Subtypes should be usable wherever their base type is expected without breaking correctness.

### 74. What is Interface Segregation Principle?

Clients should not be forced to depend on interfaces they do not use.

### 75. What is Dependency Inversion Principle?

High-level policy should not depend directly on low-level implementation details; abstractions should separate them.

### 76. Why prefer composition in many designs?

Composition often produces looser coupling and allows behavior to be changed by replacing components.

### 77. What is method resolution in multiple inheritance?

Python searches according to the class's MRO.

### 78. Why is MRO important?

It determines which implementation is found first and makes cooperative multiple inheritance possible.

### 79. What is metaprogramming?

Writing programs that manipulate or generate program structures such as classes and functions.

### 80. How would you design a real-world OOP application?

Start by identifying:

```text
Entities
Responsibilities
Relationships
Interfaces
Dependencies
State
Behavior
```

Then design classes around cohesive responsibilities and use composition, abstraction, and polymorphism where they improve the architecture.

---

# 🎯 OOP INTERVIEW RAPID REVISION

Remember these relationships:

```text
Class
  ↓
Object
  ↓
Attributes + Methods
```

```text
Encapsulation
→ Protect/control data
```

```text
Abstraction
→ Hide implementation
```

```text
Inheritance
→ Reuse/extend behavior
```

```text
Polymorphism
→ Same interface, different behavior
```

```text
Composition
→ HAS-A
```

```text
Inheritance
→ IS-A
```

```text
self
→ Current object
```

```text
cls
→ Current class
```

```text
__new__
→ Create/return instance
```

```text
__init__
→ Initialize instance
```

```text
super()
→ Access inherited behavior through MRO
```

```text
@classmethod
→ Class-level behavior
```

```text
@staticmethod
→ Utility behavior without self/cls
```

```text
@property
→ Attribute-style controlled access
```

```text
ABC
→ Define abstract interface
```

```text
__get__, __set__
→ Descriptor protocol
```

```text
type
→ Default metaclass
```

---

# 🧪 PRACTICE CHALLENGES

After completing the modules, implement these without looking at solutions.

## Beginner

### Challenge 1 — Student

Create:

```python
Student
```

with:

* name
* roll number
* marks

Methods:

```text
display()
calculate_grade()
```

---

### Challenge 2 — Bank Account

Implement:

```text
deposit()
withdraw()
balance()
```

with validation.

---

### Challenge 3 — Employee

Implement:

```text
Employee
```

with:

* class variable
* instance variables
* class method
* static method

---

## Intermediate

### Challenge 4 — Shopping Cart

Classes:

```text
Product
Cart
```

Implement:

```text
add_product()
remove_product()
calculate_total()
```

---

### Challenge 5 — Library

Classes:

```text
Book
Member
Library
```

Implement:

```text
borrow()
return_book()
search()
```

---

### Challenge 6 — Payment System

Create:

```text
PaymentProcessor
   |
   ├── CreditCard
   ├── UPI
   └── PayPal
```

Use:

* ABC
* inheritance
* polymorphism

---

## Advanced

### Challenge 7 — Custom List

Implement:

```text
__len__
__getitem__
__iter__
```

---

### Challenge 8 — Custom Context Manager

Create:

```python
with DatabaseConnection() as db:
    ...
```

---

### Challenge 9 — Descriptor

Create:

```python
PositiveNumber
```

that only accepts values greater than zero.

---

### Challenge 10 — Mini ORM

Create:

```python
User
Product
Order
```

with descriptors for validation.

---

# 🧠 COMMON OOP MISTAKES

## Mistake 1

Forgetting `self`.

Wrong:

```python
class Student:

    def display():
        print("Hello")
```

Correct:

```python
class Student:

    def display(self):
        print("Hello")
```

---

## Mistake 2

Confusing class and instance variables.

```python
class Student:
    school = "ABC"
```

is different from:

```python
self.name = "Sandesh"
```

---

## Mistake 3

Using inheritance when composition is better.

Don't create inheritance simply for code reuse.

Ask:

```text
IS-A?
```

or:

```text
HAS-A?
```

---

## Mistake 4

Thinking `_variable` is truly private.

It is primarily a convention.

---

## Mistake 5

Confusing `__new__()` and `__init__()`.

Remember:

```text
__new__ → create
__init__ → initialize
```

---

# 📈 RECOMMENDED LEARNING ORDER

Follow this sequence:

```text
Python Basics
     ↓
Functions
     ↓
Classes & Objects
     ↓
self
     ↓
__init__
     ↓
Instance Variables
     ↓
Class Variables
     ↓
Instance/Class/Static Methods
     ↓
Encapsulation
     ↓
Properties
     ↓
Inheritance
     ↓
super()
     ↓
Method Overriding
     ↓
Polymorphism
     ↓
Duck Typing
     ↓
Composition
     ↓
Dunder Methods
     ↓
MRO
     ↓
ABC
     ↓
Context Managers
     ↓
Descriptors
     ↓
Decorators
     ↓
Metaclasses
     ↓
Design Patterns
     ↓
Projects
     ↓
Interview Questions
```

---

# 💼 INTERVIEW PREPARATION STRATEGY

For every OOP concept, prepare three things:

## 1. Definition

Example:

> Encapsulation is the bundling of data and behavior while controlling access to internal state.

## 2. Code

Be able to write a small example without Google.

## 3. Real-world example

Example:

```text
BankAccount
```

for encapsulation.

```text
Vehicle → Car
```

for inheritance.

```text
PaymentProcessor → Stripe/PayPal
```

for abstraction and polymorphism.

---

# ⭐ MOST IMPORTANT QUESTIONS TO MASTER

If you have limited interview preparation time, prioritize:

1. Class vs Object
2. `self`
3. `__init__`
4. Instance vs Class Variables
5. Instance vs Class vs Static Methods
6. Encapsulation
7. Abstraction
8. Inheritance
9. Types of inheritance
10. Polymorphism
11. Method Overriding
12. Method Overloading
13. Duck Typing
14. `super()`
15. MRO
16. C3 Linearization
17. Composition vs Inheritance
18. `@property`
19. Dunder methods
20. `__str__` vs `__repr__`
21. `__new__` vs `__init__`
22. ABC
23. Context Managers
24. Descriptors
25. Metaclasses
26. Decorators
27. Singleton
28. Factory Pattern
29. SOLID principles
30. Dependency Injection

---

# 🏆 FINAL OOP CHECKLIST

Before saying **"I know Python OOP"**, make sure you can explain and code:

* [ ] Class
* [ ] Object
* [ ] `self`
* [ ] `__init__`
* [ ] Instance variables
* [ ] Class variables
* [ ] Instance methods
* [ ] Class methods
* [ ] Static methods
* [ ] Encapsulation
* [ ] Public/protected/private conventions
* [ ] Name mangling
* [ ] Abstraction
* [ ] ABC
* [ ] `@abstractmethod`
* [ ] Inheritance
* [ ] Multiple inheritance
* [ ] `super()`
* [ ] Method overriding
* [ ] Method overloading
* [ ] Polymorphism
* [ ] Duck typing
* [ ] Dynamic binding
* [ ] Composition
* [ ] Association
* [ ] Aggregation
* [ ] Dunder methods
* [ ] Operator overloading
* [ ] `__str__`
* [ ] `__repr__`
* [ ] `__eq__`
* [ ] `__add__`
* [ ] `__len__`
* [ ] `__getitem__`
* [ ] `__call__`
* [ ] Context managers
* [ ] `__enter__`
* [ ] `__exit__`
* [ ] MRO
* [ ] C3 Linearization
* [ ] Properties
* [ ] Descriptors
* [ ] Decorators
* [ ] Callable objects
* [ ] `__new__`
* [ ] Metaclasses
* [ ] Singleton
* [ ] Factory Pattern
* [ ] SOLID
* [ ] Dependency Injection
* [ ] Composition over inheritance

---

# 🚀 FINAL GOAL

The objective of this course is not simply to memorize OOP definitions.

You should be able to look at a real application and think:

```text
What are my entities?
        ↓
What data does each entity own?
        ↓
What behavior belongs to each entity?
        ↓
Which relationships exist?
        ↓
IS-A or HAS-A?
        ↓
Where should abstraction be used?
        ↓
Where should polymorphism be used?
        ↓
Should I use inheritance or composition?
        ↓
How can I keep responsibilities separated?
        ↓
Can the design be easily extended?
```

That is the difference between **knowing Python syntax** and **thinking like a Python developer**.

---

# 📚 Source Structure

This guide expands the original OOP material into a theory-first learning path while retaining its hands-on structure of **20 labs, 5 mini-projects, and interview preparation**.

The original material's advanced section includes dunder methods, custom containers, context managers, ABCs, callable objects, Singleton, Factory, decorators, descriptors, and metaclasses; these are retained here as the advanced progression.

---

# 🎓 Completion Target

After completing this README, you should be ready to:

**Python Basics → OOP → Advanced Python → Backend/Flask → FastAPI → Django → AI/ML → GenAI**

and confidently answer Python OOP questions in technical interviews.
