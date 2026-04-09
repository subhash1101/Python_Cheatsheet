AMA
---

### **Some features of Django**

* Fast development
* ORM for database handling
* Secure (protection against common attacks)
* Scalable and reusable components

---

### **Difference between try-catch and if-else**

* `try-catch` is used to handle runtime errors (exceptions)
* `if-else` is used for conditional logic based on conditions

Example:

```python
# try-except
try:
    x = 10 / 0
except:
    print("Error")

# if-else
if x > 5:
    print("Greater")
else:
    print("Smaller")
```

---

### **What is ORM**

ORM (Object Relational Mapping) allows you to interact with the database using Python code instead of SQL.

---

### **What is inversion of control**

Inversion of Control in JavaScript is a design principle where the control of program flow is transferred from your custom code to an external framework, library, or container

It mainly happens in the callbackhell, to prevent it we use promises.

---

### **What are CRUD operations**

CRUD stands for:

* Create (insert data)
* Read (get data)
* Update (modify data)
* Delete (remove data)

---

### **How you get data from API**

Using `fetch` or libraries like `requests`

Example (Python):

```python
import requests
res = requests.get("https://api.example.com")
data = res.json()
```

---

### **How to convert JSON to object and vice versa in JavaScript**

* **JSON to Object:**

```javascript
const obj = JSON.parse(jsonString);
```

* **Object to JSON:**

```javascript
const jsonString = JSON.stringify(obj);
```

---

### **What is virtual environment and why it is used**

A virtual environment is an isolated space for Python projects.

Why use it:

* Avoid dependency conflicts
* Different projects can use different versions of libraries

---

### **What is hyperlink**

A hyperlink is a clickable link that takes you to another page or resource.

Example:

```html
<a href="https://example.com">Click here</a>
```

---

### **What is callback function**

A callback function is a function passed as an argument to another function and executed later.

Example:

```javascript
function greet(name, callback) {
    callback(name);
}
```

---

### **What is head and body in network packet**

* **Header**: Contains metadata (source, destination, protocol info)
* **Body**: Contains actual data being sent

---

### **How to access HTML in Django**

Using templates and `render()` function:

```python
return render(request, 'index.html')
```

---

### **What is a global object in browser**

The global object in a browser is `window`.

It contains:

* Variables
* Functions
* Browser APIs

Example:

```javascript
window.alert("Hello")
```

---

### **What is technique to convert JSON to object and vice versa in Django**

Same as Python `json` module:

```python
import json

json.loads()   # JSON → object  
json.dumps()   # object → JSON  
```

---

### **How to see all migrations**

Command:

```bash
python manage.py showmigrations
```
