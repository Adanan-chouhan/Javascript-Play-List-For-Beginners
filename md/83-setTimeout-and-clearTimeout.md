`setTimeout` is a JavaScript method used to execute a function or code after a specified delay (in milliseconds). Unlike `setInterval`, it runs only once.

---

### Syntax:
```javascript
let timeoutId = setTimeout(callbackFunction, delay, param1, param2, ...);
```

- **`callbackFunction`**: The function to execute after the delay.
- **`delay`**: Time in milliseconds (1000ms = 1 second).
- **`param1, param2, ...`**: Optional parameters passed to the callback.
- **`timeoutId`**: A unique identifier to manage the timeout (useful for cancellation).

---

### Example 1: Simple Delay
```javascript
setTimeout(() => {
  console.log("This message appears after 3 seconds.");
}, 3000);
```

### Example 2: Using Parameters
```javascript
function greet(name) {
  console.log(`Hello, ${name}!`);
}

setTimeout(greet, 2000, "Adnan"); // Executes after 2 seconds
```

---

### Canceling a Timeout: `clearTimeout`
To stop a scheduled timeout:
```javascript
let timeoutId = setTimeout(() => {
  console.log("This will not run.");
}, 5000);

clearTimeout(timeoutId);
console.log("Timeout canceled.");
```

---

### Practical Example: DOM Interaction
```html
<button id="show">Click Me</button>
<p id="message"></p>

<script>
  document.getElementById("show").addEventListener("click", () => {
    setTimeout(() => {
      document.getElementById("message").textContent = "Message shown after 5 seconds!";
    }, 5000);
  });
</script>
```

---

### Key Points:
- Executes a function **once** after a delay.
- Use `clearTimeout` to cancel it.
- Useful for delays, animations, or simulating asynchronous behavior.