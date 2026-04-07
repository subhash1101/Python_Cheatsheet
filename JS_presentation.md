## 1. How JavaScript Executes Code

JavaScript is a **single-threaded, synchronous language** by default.

### 🔹 Execution Flow:

1. **Global Execution Context (GEC)** is created.
2. Code runs line-by-line (top → bottom).
3. Uses a **Call Stack**:

   * Functions are pushed when called.
   * Popped when execution completes.

### 🔹 Example:

```js
function a() {
  console.log("A");
}

function b() {
  console.log("B");
}

a();
b();
```

Execution Order:

* `a()` pushed → executed → popped
* `b()` pushed → executed → popped

---

## 2. Difference Between Synchronous & Asynchronous

### Synchronous (Blocking)

* Executes **line by line**
* Next task waits for previous one

```js
console.log("Start");
console.log("End");
```

Output:

```
Start
End
```

---

### Asynchronous (Non-blocking)

* Does NOT wait
* Moves to next line immediately

```js
console.log("Start");

setTimeout(() => {
  console.log("Async Task");
}, 1000);

console.log("End");
```

Output:

```
Start
End
Async Task
```

---

##  3. Ways to Make Code Asynchronous

### Callbacks

```js
setTimeout(() => {
  console.log("Callback executed");
}, 1000);
```

---

### Promises

```js
const promise = new Promise((resolve, reject) => {
  resolve("Done");
});

promise.then((res) => console.log(res));
```

---

### Async/Await

```js
async function run() {
  let res = await Promise.resolve("Done");
  console.log(res);
}

run();
```

---

### Browser APIs (Async by nature)

* `setTimeout`
* `fetch`
* `DOM events`

---

## 4. What are Web Browser APIs?

These are **features provided by the browser**
### Examples:

* `setTimeout()`
* `fetch()`
* DOM APIs (`document.getElementById`)


 They run outside JS engine and return results later.

---

##  5. What is the Event Loop?

The **Event Loop** manages async execution.

### 🔹 Components:

* Call Stack
* Web APIs
* Callback Queue (Task Queue)
* Microtask Queue (Promises)

### 🔹 Flow:

1. Sync code runs first
2. Async tasks go to Web APIs
3. After completion → moved to queue
4. Event loop pushes them to stack when empty

### 🔹 Example:

```js
console.log("Start");

setTimeout(() => console.log("Timeout"), 0);

Promise.resolve().then(() => console.log("Promise"));

console.log("End");
```

 Output:

```
Start
End
Promise
Timeout
```

 Why?

* Promises → **Microtask Queue (higher priority)**
* setTimeout → **Callback Queue**

---

##  6. What is a Promise?

A Promise represents **future completion of an async task**

### States:

* Pending
* Fulfilled
* Rejected

```js
fetch("https://api.com")
  .then(res => res.json())
  .then(data => console.log(data))
  .catch(err => console.error(err));
```

---

## 7. What is Callback Hell?

When callbacks are nested deeply → hard to read & maintain

```js
setTimeout(() => {
  console.log("Step 1");
  setTimeout(() => {
    console.log("Step 2");
    setTimeout(() => {
      console.log("Step 3");
    }, 1000);
  }, 1000);
}, 1000);
```

Problems:

* Pyramid structure
* Hard debugging
* Poor readability

---

##  8. What is Inversion of Control (IoC) in Callbacks?

You **give control** of your function to another function

```js
function fetchData(callback) {
  setTimeout(() => {
    callback("Data received");
  }, 1000);
}

fetchData((data) => {
  console.log(data);
});
```