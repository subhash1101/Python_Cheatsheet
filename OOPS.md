# Object-Oriented Programming (OOP)

Object-Oriented Programming (OOP) is a way of writing programs using **classes** and **objects**.
This makes programs easier to understand, reuse, and manage.

---

# Class

A **class** is like a blueprint or template.
It defines what an object will have (data) and what it can do (methods).

### Example:

```python
class Car:
    pass
```

Here, `Car` is just a blueprint.
It does not create anything yet.

---

# Object

An **object** is a real thing created from a class.

```python
c1 = Car()
print(type(c1))
# Output: <class '__main__.Car'>
```

`c1` is now an object of class `Car`.

---

## Constructor – `__init__`

The constructor runs automatically when we create an object.

It is used to give initial values.

```python
class Car:
    def __init__(self, brand, speed):
        self.brand = brand
        self.speed = speed

car1 = Car("Toyota", 120)

print(car1.brand)  
# Output: Toyota

print(car1.speed)  
# Output: 120
```

`self` means the current object.

---

## Instance Methods

Methods are functions inside a class.

```python
class Car:
    def __init__(self, brand):
        self.brand = brand

    def start(self):
        return f"{self.brand} is starting..."

c = Car("BMW")
print(c.start())
# Output: BMW is starting...
```

---

## `__str__()` – Readable Format

This method decides what prints when we use `print(object)`.

---

# Inheritance (Reusing Code)

Inheritance allows one class to use features of another class.

```python
class Vehicle:
    def move(self):
        return "Vehicle is moving"

class Bike(Vehicle):
    pass

b = Bike()
print(b.move())
# Output: Vehicle is moving
```

`Bike` automatically gets the `move()` method.

---

## Using `super()`

`super()` is used to call the parent class constructor.

```python
class Vehicle:
    def __init__(self, type_name):
        self.type_name = type_name

class Bus(Vehicle):
    def __init__(self, type_name, seats):
        super().__init__(type_name)
        self.seats = seats

bus1 = Bus("Public Bus", 50)
print(bus1.type_name)
# Output: Public Bus

print(bus1.seats)
# Output: 50
```

---

# Encapsulation (Protecting Data)

Encapsulation means hiding important data from direct access.

### Types:

* Public → `self.name`
* Protected → `self._name` (just a rule, not strict)
* Private → `self.__name` (strong protection)

```python
class Account:
    def __init__(self, balance):
        self.__balance = balance

    def add_money(self, amount):
        self.__balance += amount

    def check_balance(self):
        return self.__balance

acc = Account(1000)
acc.add_money(500)

print(acc.check_balance())
# Output: 1500
```

```python
print(acc.__balance)
# Output: AttributeError
```

---

## Class Variables (Shared Data)

Class variables are shared by all objects.

```python
class Student:
    school = "ABC School"

s1 = Student()
s2 = Student()

print(s1.school)
# Output: ABC School

print(s2.school)
# Output: ABC School
```

---

# Static Method

A static method does not use object data.

```python
class Calculator:
    @staticmethod
    def multiply(a, b):
        return a * b

print(Calculator.multiply(3, 4))
# Output: 12
```

---

## Class Method

A class method works with the class itself.

```python
class Employee:
    company = "TechCorp"

    @classmethod
    def change_company(cls, name):
        cls.company = name

Employee.change_company("InnovateX")

print(Employee.company)
# Output: InnovateX
```

---

# Four Main Principles of OOP

---

## 1. Encapsulation

Keep data and methods together and protect important data.

 Example: Private balance in bank account.

---

## 2. Abstraction

Show only necessary details and hide complex logic.

```python
from abc import ABC, abstractmethod

class Payment(ABC):
    @abstractmethod
    def pay(self, amount):
        pass
```

This forces child classes to implement `pay()`.

---

## 3. Inheritance

Child class reuses parent class features.

```python
class Bird:
    def fly(self):
        return "Flying"

class Eagle(Bird):
    pass

e = Eagle()
print(e.fly())
# Output: Flying
```

---

## 4. Polymorphism

Same method name, different behavior.

```python
class Lion:
    def sound(self):
        return "Roar"

class Cow:
    def sound(self):
        return "Moo"

def animal_sound(animal):
    print(animal.sound())

animal_sound(Lion())
# Output: Roar

animal_sound(Cow())
# Output: Moo
```

