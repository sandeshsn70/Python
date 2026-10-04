# 🐍 Python Object-Oriented Programming (OOP) Mastery

A comprehensive, hands-on guide covering Python OOP concepts from basic fundamentals to advanced architecture, complete with code solutions for 20 labs, 5 full mini-projects, and top Python OOP interview questions.

---

## 📚 Table of Contents
1. [Module 1: Core Foundations (Labs 01-05)](#module-1-core-foundations)
2. [Module 2: Intermediate OOP & Encapsulation (Labs 06-10)](#module-2-intermediate-oop--encapsulation)
3. [Module 3: Advanced OOP Concepts (Labs 11-15)](#module-3-advanced-oop-concepts)
4. [Module 4: Design Patterns & Metaprogramming (Labs 16-20)](#module-4-design-patterns--metaprogramming)
5. [🛠️ Mini-Projects (Projects 1-5)](#%EF%B8%8F-mini-projects)
6. [💡 Top Python OOP Interview Questions & Answers](#-top-python-oop-interview-questions--answers)

---

## Module 1: Core Foundations

### Lab 01: Defining Classes & Instantiating Objects
**Task:** Create a `Car` class with attributes `make`, `model`, and `year`. Write a method `get_info()` that returns a formatted summary.

```python
class Car:
    def __init__(self, make: str, model: str, year: int):
        self.make = make
        self.model = model
        self.year = year

    def get_info(self) -> str:
        return f"{self.year} {self.make} {self.model}"

# Solution Verification
if __name__ == "__main__":
    car1 = Car("Toyota", "Corolla", 2022)
    print(car1.get_info())  # Output: 2022 Toyota Corolla
```

---

### Lab 02: Instance Methods & State Modification
**Task:** Create a `BankAccount` class with `balance`. Implement `deposit(amount)` and `withdraw(amount)` with checks for invalid inputs.

```python
class BankAccount:
    def __init__(self, owner: str, balance: float = 0.0):
        self.owner = owner
        self.balance = balance

    def deposit(self, amount: float) -> float:
        if amount <= 0:
            raise ValueError("Deposit amount must be positive.")
        self.balance += amount
        return self.balance

    def withdraw(self, amount: float) -> float:
        if amount <= 0:
            raise ValueError("Withdrawal amount must be positive.")
        if amount > self.balance:
            raise ValueError("Insufficient funds.")
        self.balance -= amount
        return self.balance

# Solution Verification
if __name__ == "__main__":
    account = BankAccount("Alice", 100.0)
    account.deposit(50.0)
    account.withdraw(30.0)
    print(f"Current Balance: ${account.balance}")  # Output: 120.0
```

---

### Lab 03: Class Variables vs. Instance Variables
**Task:** Create an `Employee` class using a class variable `company_name` and `employee_count` to track instances created.

```python
class Employee:
    company_name = "Tech Corp"
    employee_count = 0

    def __init__(self, name: str, role: str):
        self.name = name
        self.role = role
        Employee.employee_count += 1

# Solution Verification
if __name__ == "__main__":
    emp1 = Employee("Alice", "Engineer")
    emp2 = Employee("Bob", "Designer")
    print(f"Company: {Employee.company_name}")
    print(f"Total Employees: {Employee.employee_count}")  # Output: 2
```

---

### Lab 04: Class Methods (`@classmethod`)
**Task:** Create a `Date` class with a class method `from_string("DD-MM-YYYY")` as an alternative constructor.

```python
class Date:
    def __init__(self, day: int, month: int, year: int):
        self.day = day
        self.month = month
        self.year = year

    @classmethod
    def from_string(cls, date_str: str):
        day, month, year = map(int, date_str.split("-"))
        return cls(day, month, year)

    def __repr__(self):
        return f"Date({self.day:02d}/{self.month:02d}/{self.year})"

# Solution Verification
if __name__ == "__main__":
    d = Date.from_string("25-12-2024")
    print(d)  # Output: Date(25/12/2024)
```

---

### Lab 05: Static Methods (`@staticmethod`)
**Task:** Create a `MathUtils` class with utility static methods `is_prime(n)` and `factorial(n)`.

```python
class MathUtils:
    @staticmethod
    def is_prime(n: int) -> bool:
        if n < 2:
            return False
        for i in range(2, int(n**0.5) + 1):
            if n % i == 0:
                return False
        return True

    @staticmethod
    def factorial(n: int) -> int:
        if n < 0:
            raise ValueError("Negative numbers not allowed.")
        return 1 if n in (0, 1) else n * MathUtils.factorial(n - 1)

# Solution Verification
if __name__ == "__main__":
    print(MathUtils.is_prime(17))     # True
    print(MathUtils.factorial(5))     # 120
```

---

## Module 2: Intermediate OOP & Encapsulation

### Lab 06: Encapsulation & Access Modifiers
**Task:** Create a `UserAccount` class with private `__password` and protected `_email`. Implement validation methods.

```python
class UserAccount:
    def __init__(self, username: str, email: str, password: str):
        self.username = username
        self._email = email          # Protected
        self.__password = password  # Private (Name Mangling)

    def verify_password(self, password: str) -> bool:
        return self.__password == password

    def update_password(self, old_pwd: str, new_pwd: str) -> bool:
        if self.verify_password(old_pwd):
            self.__password = new_pwd
            return True
        return False

# Solution Verification
if __name__ == "__main__":
    user = UserAccount("john_doe", "john@example.com", "secret123")
    print(user.verify_password("secret123"))  # True
    print(user.update_password("secret123", "new_pass"))  # True
```

---

### Lab 07: Property Decorators (`@property`, `@setter`)
**Task:** Create a `Temperature` class storing `_celsius` with dynamic getters/setters for `fahrenheit`.

```python
class Temperature:
    def __init__(self, celsius: float = 0.0):
        self._celsius = celsius

    @property
    def celsius(self) -> float:
        return self._celsius

    @celsius.setter
    def celsius(self, value: float):
        if value < -273.15:
            raise ValueError("Temperature below absolute zero is impossible.")
        self._celsius = value

    @property
    def fahrenheit(self) -> float:
        return (self._celsius * 9/5) + 32

    @fahrenheit.setter
    def fahrenheit(self, value: float):
        self.celsius = (value - 32) * 5/9

# Solution Verification
if __name__ == "__main__":
    temp = Temperature(25)
    print(temp.fahrenheit)  # 77.0
    temp.fahrenheit = 212
    print(temp.celsius)     # 100.0
```

---

### Lab 08: Single & Multiple Inheritance
**Task:** Build a class hierarchy with `Vehicle`, `ElectricCar`, and `Motorcycle` using `super()`.

```python
class Vehicle:
    def __init__(self, brand: str, speed: int):
        self.brand = brand
        self.speed = speed

    def drive(self) -> str:
        return f"{self.brand} is traveling at {self.speed} km/h."

class ElectricCar(Vehicle):
    def __init__(self, brand: str, speed: int, battery_capacity: int):
        super().__init__(brand, speed)
        self.battery_capacity = battery_capacity

    def drive(self) -> str:
        base_msg = super().drive()
        return f"{base_msg} Operating on electric battery ({self.battery_capacity} kWh)."

# Solution Verification
if __name__ == "__main__":
    ev = ElectricCar("Tesla", 120, 75)
    print(ev.drive())
```

---

### Lab 09: Method Resolution Order (MRO)
**Task:** Build a diamond inheritance setup (`A`, `B`, `C`, `D`) and observe C3 Linearization MRO.

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

# Solution Verification
if __name__ == "__main__":
    d = D()
    print(d.show())  # Output: D -> B -> C -> A
    print([cls.__name__ for cls in D.mro()]) # Show MRO list
```

---

### Lab 10: Polymorphism & Duck Typing
**Task:** Demonstrate duck typing with `PDFReport`, `CSVReport`, and `HTMLReport` rendered through a single function.

```python
class PDFReport:
    def generate(self) -> str:
        return "[PDF Document Content]"

class CSVReport:
    def generate(self) -> str:
        return "col1,col2\nval1,val2"

class HTMLReport:
    def generate(self) -> str:
        return "<html><body>Report</body></html>"

def render_report(report_obj):
    # Dynamic polymorphism via duck typing (expects generate method)
    print(f"Rendering:\n{report_obj.generate()}\n")

# Solution Verification
if __name__ == "__main__":
    reports = [PDFReport(), CSVReport(), HTMLReport()]
    for r in reports:
        render_report(r)
```

---

## Module 3: Advanced OOP Concepts

### Lab 11: Magic/Dunder Methods (Operators)
**Task:** Create a `Vector2D` class that supports addition (`+`) and equality check (`==`).

```python
class Vector2D:
    def __init__(self, x: float, y: float):
        self.x = x
        self.y = y

    def __add__(self, other):
        if isinstance(other, Vector2D):
            return Vector2D(self.x + other.x, self.y + other.y)
        return NotImplemented

    def __eq__(self, other):
        if isinstance(other, Vector2D):
            return self.x == other.x and self.y == other.y
        return False

    def __repr__(self):
        return f"Vector2D({self.x}, {self.y})"

# Solution Verification
if __name__ == "__main__":
    v1 = Vector2D(2, 4)
    v2 = Vector2D(3, 1)
    print(v1 + v2)        # Vector2D(5, 5)
    print(v1 == Vector2D(2, 4)) # True
```

---

### Lab 12: Custom Container Emulation
**Task:** Implement `__len__`, `__getitem__`, and `__iter__` on a `Playlist` class.

```python
class Playlist:
    def __init__(self, name: str):
        self.name = name
        self._songs = []

    def add_song(self, song_title: str):
        self._songs.append(song_title)

    def __len__(self):
        return len(self._songs)

    def __getitem__(self, index):
        return self._songs[index]

# Solution Verification
if __name__ == "__main__":
    pl = Playlist("Chill Vibes")
    pl.add_song("Song A")
    pl.add_song("Song B")
    print(len(pl))       # 2
    print(pl[0])         # Song A
    for song in pl:      # Iteration working automatically
        print(song)
```

---

### Lab 13: Context Managers (`__enter__` & `__exit__`)
**Task:** Create a custom resource context manager `SafeFileWriter`.

```python
class SafeFileWriter:
    def __init__(self, filepath: str, mode: str = "w"):
        self.filepath = filepath
        self.mode = mode
        self.file = None

    def __enter__(self):
        self.file = open(self.filepath, self.mode)
        return self.file

    def __exit__(self, exc_type, exc_val, exc_tb):
        if self.file:
            self.file.close()
        if exc_type:
            print(f"An error occurred: {exc_val}")
        return True  # Suppress exception for demo purposes

# Solution Verification
if __name__ == "__main__":
    with SafeFileWriter("test.txt") as f:
        f.write("Hello, Context Manager!")
```

---

### Lab 14: Abstract Base Classes (ABCs)
**Task:** Define an abstract base class `PaymentProcessor` with an abstract method `pay(amount)`.

```python
from abc import ABC, abstractmethod

class PaymentProcessor(ABC):
    @abstractmethod
    def pay(self, amount: float) -> bool:
        pass

class StripeProcessor(PaymentProcessor):
    def pay(self, amount: float) -> bool:
        print(f"Processing ${amount:.2f} via Stripe...")
        return True

class PayPalProcessor(PaymentProcessor):
    def pay(self, amount: float) -> bool:
        print(f"Processing ${amount:.2f} via PayPal...")
        return True

# Solution Verification
if __name__ == "__main__":
    processors = [StripeProcessor(), PayPalProcessor()]
    for p in processors:
        p.pay(99.99)
```

---

### Lab 15: Callable Objects (`__call__`)
**Task:** Implement `__call__` in a `Multiplier` class to create stateful function objects.

```python
class Multiplier:
    def __init__(self, factor: float):
        self.factor = factor

    def __call__(self, value: float) -> float:
        return value * self.factor

# Solution Verification
if __name__ == "__main__":
    double = Multiplier(2)
    triple = Multiplier(3)

    print(double(10)) # 20
    print(triple(10)) # 30
```

---

## Module 4: Design Patterns & Metaprogramming

### Lab 16: Singleton Pattern
**Task:** Implement a thread-safe / standard Singleton `DatabaseConnection` using `__new__`.

```python
class DatabaseConnection:
    _instance = None

    def __new__(cls, *args, **kwargs):
        if cls._instance is None:
            cls._instance = super().__new__(cls)
            cls._instance._initialized = False
        return cls._instance

    def __init__(self, db_name: str = "default.db"):
        if not self._initialized:
            self.db_name = db_name
            self._initialized = True

# Solution Verification
if __name__ == "__main__":
    db1 = DatabaseConnection("prod.db")
    db2 = DatabaseConnection("test.db")
    print(db1 is db2)       # True
    print(db1.db_name)      # prod.db
```

---

### Lab 17: Factory Pattern
**Task:** Build a `NotificationFactory` producing instances based on notification type.

```python
class Notification(ABC):
    @abstractmethod
    def send(self, message: str):
        pass

class EmailNotification(Notification):
    def send(self, message: str):
        print(f"Email sent: {message}")

class SMSNotification(Notification):
    def send(self, message: str):
        print(f"SMS sent: {message}")

class NotificationFactory:
    @staticmethod
    def create_notification(channel: str) -> Notification:
        if channel.lower() == "email":
            return EmailNotification()
        elif channel.lower() == "sms":
            return SMSNotification()
        raise ValueError(f"Unknown notification channel: {channel}")

# Solution Verification
if __name__ == "__main__":
    notifier = NotificationFactory.create_notification("email")
    notifier.send("Hello World!")
```

---

### Lab 18: Method Decorators inside Classes
**Task:** Implement a class method decorator `@audit_log` that logs execution details.

```python
import functools
import time

def audit_log(func):
    @functools.wraps(func)
    def wrapper(*args, **kwargs):
        start = time.time()
        result = func(*args, **kwargs)
        duration = time.time() - start
        print(f"[AUDIT] Method '{func.__name__}' executed in {duration:.6f}s")
        return result
    return wrapper

class DataService:
    @audit_log
    def process_data(self, data: list):
        return [x * 2 for x in data]

# Solution Verification
if __name__ == "__main__":
    service = DataService()
    service.process_data([1, 2, 3, 4, 5])
```

---

### Lab 19: Custom Descriptors
**Task:** Build a `BoundedNumber` descriptor restricting numerical attributes to a specific range.

```python
class BoundedNumber:
    def __init__(self, min_val: float, max_val: float):
        self.min_val = min_val
        self.max_val = max_val

    def __set_name__(self, owner, name):
        self.private_name = f"_{name}"

    def __get__(self, instance, owner):
        if instance is None:
            return self
        return getattr(instance, self.private_name, self.min_val)

    def __set__(self, instance, value: float):
        if not (self.min_val <= value <= self.max_val):
            raise ValueError(f"Value must be between {self.min_val} and {self.max_val}")
        setattr(instance, self.private_name, value)

class Character:
    health = BoundedNumber(0, 100)

    def __init__(self, health: float):
        self.health = health

# Solution Verification
if __name__ == "__main__":
    hero = Character(80)
    hero.health = 100
    print(hero.health)  # 100
    # hero.health = 150 # Raises ValueError
```

---

### Lab 20: Metaclasses (`type`)
**Task:** Implement a metaclass `RequireDocstringsMeta` enforcing docstrings on all methods.

```python
class RequireDocstringsMeta(type):
    def __new__(mcs, name, bases, attrs):
        for key, val in attrs.items():
            if callable(val) and not key.startswith("__"):
                if not val.__doc__:
                    raise TypeError(f"Method '{key}' in class '{name}' must have a docstring.")
        return super().__new__(mcs, name, bases, attrs)

# Solution Verification
try:
    class ValidClass(metaclass=RequireDocstringsMeta):
        def compute(self):
            """Computes sample value."""
            return 42

    print("Class created successfully.")
except TypeError as e:
    print(e)
```

---

## 🛠️ Mini-Projects

### Project 1: Bank Account Management System

```python
from abc import ABC, abstractmethod

class TransactionContext:
    def __init__(self, account):
        self.account = account

    def __enter__(self):
        print(f"[TX START] Account: {self.account.account_number}")
        return self

    def __exit__(self, exc_type, exc_val, exc_tb):
        if exc_type:
            print(f"[TX FAILED] Transaction aborted: {exc_val}")
            return True
        print(f"[TX SUCCESS] New Balance: ${self.account.balance:.2f}")
        return True

class Account(ABC):
    def __init__(self, account_number: str, owner: str, balance: float = 0.0):
        self.account_number = account_number
        self.owner = owner
        self._balance = balance

    @property
    def balance(self) -> float:
        return self._balance

    @abstractmethod
    def withdraw(self, amount: float):
        pass

    def deposit(self, amount: float):
        if amount <= 0:
            raise ValueError("Amount must be positive.")
        self._balance += amount

class SavingsAccount(Account):
    def __init__(self, account_number: str, owner: str, balance: float, interest_rate: float):
        super().__init__(account_number, owner, balance)
        self.interest_rate = interest_rate

    def withdraw(self, amount: float):
        if amount > self._balance:
            raise ValueError("Insufficient balance in savings.")
        self._balance -= amount

    def apply_interest(self):
        self._balance += self._balance * self.interest_rate

# Demo
if __name__ == "__main__":
    acc = SavingsAccount("SA-1001", "Alice", 500.0, 0.05)
    with TransactionContext(acc):
        acc.deposit(200.0)
        acc.withdraw(100.0)
```

---

### Project 2: Library & Book Reservation System

```python
class Book:
    def __init__(self, title: str, author: str, isbn: str):
        self.title = title
        self.author = author
        self.isbn = isbn
        self.is_borrowed = False

    def __repr__(self):
        return f"Book('{self.title}', '{self.author}')"

class Library:
    def __init__(self, name: str):
        self.name = name
        self._books = []

    def add_book(self, book: Book):
        self._books.append(book)

    def __getitem__(self, index):
        return self._books[index]

    def __len__(self):
        return len(self._books)

    def search_by_title(self, title: str):
        return [b for b in self._books if title.lower() in b.title.lower()]

# Demo
if __name__ == "__main__":
    lib = Library("City Central Library")
    lib.add_book(Book("Fluent Python", "Luciano Ramalho", "9781491946008"))
    lib.add_book(Book("Clean Code", "Robert C. Martin", "9780132350884"))

    print(f"Total Books: {len(lib)}")
    print(f"First Book: {lib[0]}")
```

---

### Project 3: Terminal RPG Engine

```python
from abc import ABC, abstractmethod

class Character(ABC):
    def __init__(self, name: str, health: int, attack_power: int):
        self.name = name
        self.health = health
        self.attack_power = attack_power

    @abstractmethod
    def attack(self, target: "Character"):
        pass

    def is_alive(self) -> bool:
        return self.health > 0

class Warrior(Character):
    def attack(self, target: Character):
        damage = self.attack_power + 5
        target.health -= damage
        print(f"⚔️ {self.name} strikes {target.name} for {damage} damage!")

class Mage(Character):
    def attack(self, target: Character):
        damage = self.attack_power + 10
        target.health -= damage
        print(f"🔮 {self.name} casts spell on {target.name} for {damage} damage!")

# Demo
if __name__ == "__main__":
    hero = Warrior("Conan", 100, 15)
    monster = Mage("Goblin Mage", 50, 10)

    hero.attack(monster)
    print(f"Monster Health: {monster.health}")
```

---

### Project 4: Custom Object-Relational Mapper (ORM) Lightweight Engine

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
            raise TypeError(f"Expected {self.field_type.__name__}, got {type(value).__name__}")
        instance.__dict__[self.name] = value

class ModelMeta(type):
    def __new__(mcs, name, bases, attrs):
        fields = {k: v for k, v in attrs.items() if isinstance(v, Field)}
        attrs["_fields"] = fields
        return super().__new__(mcs, name, bases, attrs)

class Model(metaclass=ModelMeta):
    def save(self):
        data = {field: getattr(self, field) for field in self._fields}
        print(f"Saving {self.__class__.__name__} to DB: {data}")

class User(Model):
    name = Field(str)
    age = Field(int)

# Demo
if __name__ == "__main__":
    u = User()
    u.name = "Alice"
    u.age = 30
    u.save()
```

---

### Project 5: Event-Driven Task Scheduler Engine

```python
import time

class Scheduler:
    _instance = None

    def __new__(cls):
        if cls._instance is None:
            cls._instance = super().__new__(cls)
            cls._instance.tasks = []
        return cls._instance

    def register_task(self, name: str, func):
        self.tasks.append({"name": name, "func": func})

    def run_all(self):
        print("Starting task execution...")
        for t in self.tasks:
            print(f"Executing [{t['name']}]...")
            t["func"]()
            print(f"Completed [{t['name']}]")

# Demo
if __name__ == "__main__":
    scheduler = Scheduler()
    scheduler.register_task("Data Sync", lambda: time.sleep(0.1))
    scheduler.register_task("Cleanup", lambda: print("Cleaned temporary files."))
    scheduler.run_all()
```

---

## 💡 Top Python OOP Interview Questions & Answers

### 1. What is the difference between `__new__` and `__init__`?
*   `__new__` is the actual constructor responsible for creating and returning a new instance of a class. It is a static method (implicitly).
*   `__init__` is the initializer method responsible for setting up attributes once the object is already created.

### 2. What is Method Resolution Order (MRO) and how does C3 Linearization work?
*   MRO dictates the order in which Python searches for methods across class inheritance hierarchies, particularly in multiple inheritance setups.
*   Python uses the **C3 Linearization Algorithm**, guaranteeing monotonicity and respecting local precedence order. You can view a class's MRO using `ClassName.mro()` or `ClassName.__mro__`.

### 3. How does Duck Typing work in Python?
*   Duck typing comes from the phrase *"If it walks like a duck and quacks like a duck, it's a duck."*
*   Python focuses on an object's interface (what methods and attributes it supports) rather than its explicit class hierarchy. Type safety is checked at runtime when a method or property is called.

### 4. What are Descriptors and how do they differ from `@property`?
*   Descriptors are reusable objects that define how attribute access is managed via `__get__`, `__set__`, and `__delete__` methods.
*   `@property` is a built-in convenience decorator that creates a descriptor under the hood for single class attributes. Custom descriptors allow you to share attribute validation logic across multiple attributes and classes.

### 5. Explain the difference between Class Methods, Static Methods, and Instance Methods.
*   **Instance Method:** Takes `self` as the first argument; operates on specific object instances.
*   **Class Method (`@classmethod`):** Takes `cls` as the first argument; operates on class-level attributes and can act as alternative constructors.
*   **Static Method (`@staticmethod`):** Receives neither `self` nor `cls`; acts as a utility function namespaced inside the class context.
