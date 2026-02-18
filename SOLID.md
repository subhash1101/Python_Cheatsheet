# SOLID Principles

SOLID is a set of 5 important rules in Object-Oriented Programming.

---

# S – Single Responsibility Principle (SRP)

### Simple Meaning:

A class should do only **one job**.
If a class is doing many things, it becomes hard to manage.

---

### Correct Code

```python
class InvoiceCalculator:
    def calculate_total(self, items):
        return sum(items)

class InvoicePrinter:
    def print_invoice(self, total):
        print(f"Total: {total}")

calc = InvoiceCalculator()
printer = InvoicePrinter()

total = calc.calculate_total([100, 200])
printer.print_invoice(total)

# Output:
# Total: 300
```

Now each class has only **one responsibility**.

---

# O – Open/Closed Principle (OCP)

### Simple Meaning:

You should be able to **add new features** without changing old code.

---

### Correct Code

```python
class Shape:
    def area(self):
        pass

class Square(Shape):
    def __init__(self, side):
        self.side = side

    def area(self):
        return self.side * self.side

class Circle(Shape):
    def __init__(self, radius):
        self.radius = radius

    def area(self):
        return 3.14 * self.radius * self.radius

s = Square(4)
print(s.area())

# Output:
# 16
```

Now we can add new shapes without touching old code.

---

#  L – Liskov Substitution Principle (LSP)

### Simple Meaning:

A child class should behave properly like its parent.
You should be able to replace parent with child without breaking code.

---


### Correct Code

```python
class Vehicle:
    pass

class EngineVehicle(Vehicle):
    def start_engine(self):
        return "Engine started"

class Car(EngineVehicle):
    pass

car = Car()
print(car.start_engine())

# Output:
# Engine started
```

---

# I – Interface Segregation Principle (ISP)

### Simple Meaning:

Do not force a class to implement methods it doesn’t need.

Keep things small and specific.

---


### Correct Code

```python
class Printer:
    def print_doc(self):
        print("Printing...")

class Scanner:
    def scan_doc(self):
        print("Scanning...")

p = Printer()
p.print_doc()

# Output:
# Printing...
```

Each class has only needed behavior.

---

# D – Dependency Inversion Principle (DIP)

### Simple Meaning:

High-level classes should not depend directly on low-level classes.
Both should depend on a general rule (abstraction).

---

### Correct Code

```python
class InputDevice:
    def type(self):
        pass

class Keyboard(InputDevice):
    def type(self):
        return "Typing..."

class Computer:
    def __init__(self, device: InputDevice):
        self.device = device

    def use_device(self):
        return self.device.type()

keyboard = Keyboard()
computer = Computer(keyboard)

print(computer.use_device())

# Output:
# Typing...
```

Now we can replace Keyboard with another device easily.

---
