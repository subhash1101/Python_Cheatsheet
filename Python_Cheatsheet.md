# Python Cheatsheet

# Hello World

```python
print("Hello World")  # Hello World
````
---
# Data Types

```python
type(1)  # int
type(2.3)  # float
type(True)  # bool
type("Hello World")  # str
```

---

# Operators


Arthematic Operators:

```python
+  -  *  /  **  %  //
```

---


Comparison:

```python
== != > < >= <=
```

Boolean:

```python
and or not
```

---
# Conditional Statements

```python
age = 18

if age=18:
    print("You're an adult!")  # You're an adult!
elif age>18:
    print("You're an big adult!")
else:
    print("You're small child!")
```

Membership check:

```python
'China' in ['United States','India','China','Brazil']  # True
```

---

# For Loop

```python
countries = ['United States','India','China','Brazil']

for country in countries:
    print(country)
# United States
# India
# China
# Brazil
```

Enumerate:

```python
for i,country in enumerate(countries):
    print(i,country)
# 0 United States
# 1 India
# 2 China
# 3 Brazil
```
---

# Functions

Built-in Functions:

```
range() len() max() min() round() type()
```

Custom Function:

```python
def sum_values(a,b):
    return a+b

sum_values(2,3)  # 5
```
---

# String Methods

```python

"Hello World".upper()              # HELLO WORLD
"Hello World".lower()              # hello world
"hello world".title()              # Hello World
"hello world".count('l')           # 3
"hello world".replace('o','u')     # hellu wurld

" hello ".strip()                  # hello
" hello ".lstrip()                 # hello 
" hello ".rstrip()                 #  hello
"hello".capitalize()               # Hello
"HELLO".casefold()                 # hello
"hello".center(10,'-')             # --hello---
"42".zfill(5)                      # 00042
"hello world".startswith("hello")  # True
"hello world".endswith("world")    # True
"apple,banana".split(",")          # ['apple', 'banana']
"-".join(["a","b","c"])            # a-b-c
"hello123".isalnum()               # True
"hello".isalpha()                  # True
"123".isdigit()                    # True
"hello world".find("world")        # 6
"hello world".index("world")       # 6
"pyTHon".swapcase()                # PYthON
"line1\nline2".splitlines()        # ['line1', 'line2']
```
---

# Variables

```python
message_1 = "I'm learning Java"
message_1  # I'm learning Java

message_2 = "and it's boring!"
```

---

# String Concatenation

```python
message_1 + message_2  # I'm learning Javaand it's boring!

message = message_1 + ' ' + message_2
message  # I'm learning Java and it's boring!

message = f'{message_1} {message_2}'
message  # I'm learning Java and it's boring!
```

---

# Lists

```python
countries = ['United States','India','China','Brazil']
```

## Indexing

```python
countries[0]  # United States
countries[1]  # India
countries[2]  # China
countries[3]  # Brazil
countries[-1]  # Brazil
```

---

## Slicing

```python
countries[0:3]  # ['United States','India','China']
countries[1:]   # ['India','China','Brazil']
countries[:2]   # ['United States','India']
```

---

## Adding Elements

```python
countries.append('Canada')  
# ['United States','India','China','Brazil','Canada']

countries.insert(0,'Canada')  
# ['Canada','United States','India','China','Brazil']

countries_2 = ['UK','Germany','Austria']
countries + countries_2  
# ['Canada','United States','India','China','Brazil','UK','Germany','Austria']

nested_list = [countries,countries_2]
# [['Canada','United States','India','China','Brazil'],['UK','Germany','Austria']]
```

---

## Removing Elements

```python
countries = ['United States','India','China','Brazil']
countries.remove('United States')  # ['India','China','Brazil']
countries.pop(0)  # removes 'India'
del countries[0]  # removes 'China'
countries  # ['Brazil']
```

---

## Sorting Lists

```python
numbers = [4,3,10,7,1,2]
numbers.sort()
numbers  # [1,2,3,4,7,10]

numbers.sort(reverse=True)
numbers  # [10,7,4,3,2,1]
```

---

## Update List Value

```python
numbers[0] = 1000
numbers  # [1000,7,4,3,2,1]
```

---

## Copy Lists

```python
new_list = countries[:]  # ['Brazil']
new_list_2 = countries.copy()  # ['Brazil']
```

---

# Dictionary

```python
my_data = {'name':'Frank','age':26}

my_data['name']  # Frank
my_data.keys()  # dict_keys(['name','age'])
my_data.values()  # dict_values(['Frank',26])
my_data.items()  # dict_items([('name','Frank'),('age',26)])
```

---

## Add / Update Dictionary

```python
my_data['height']=1.7
my_data.update({'height':1.8,'languages':['English','Spanish']})
# {'name':'Frank','age':26,'height':1.8,'languages':['English','Spanish']}
```

---

## Copy Dictionary

```python
new_dict = my_data.copy()
# {'name':'Frank','age':26,'height':1.8,'languages':['English','Spanish']}
```

---

## Remove Dictionary Elements

```python
my_data.pop('height')  # 1.8
del my_data['languages']
my_data.clear()
my_data  # {}
```

---


Dictionary loop:

```python
for key,value in {'name':'Frank','age':26}.items():
    print(key,value)
# name Frank
# age 26

```

---
