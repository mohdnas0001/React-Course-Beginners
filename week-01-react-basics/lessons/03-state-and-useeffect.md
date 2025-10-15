`week-01-react-basics/lessons/03-state-and-useeffect.md`

---

## 📘 **03-state-and-useeffect.md**

````markdown
# Lesson 3: State and useEffect in React

---

## 🧠 What Is State?

**State** is how a component *remembers* things.

Think of it as your app’s short-term memory.  
When data changes (like user input, button clicks, or fetched data), React re-renders the component with the new state.

---

## ⚙️ Declaring State with `useState`

React gives us a special hook called `useState`.
````

```jsx
import { useState } from "react";

function Counter() {
  const [count, setCount] = useState(0); // [value, updater function]

  return (
    <div>
      <h2>Count: {count}</h2>
      <button onClick={() => setCount(count + 1)}>Increase</button>
    </div>
  );
}
````

✅ Explanation:

* `count` → current value
* `setCount` → function to update the value
* `useState(0)` → initializes `count` with 0

---

## 🔁 How React Updates State

When you call `setCount(count + 1)`, React:

1. Updates the internal value of `count`
2. Re-renders the component with the new value

So if you click the button 5 times, it re-renders 5 times — automatically.

---

## ⚡ Multiple State Values

You can track multiple things with different `useState` calls:


```jsx
function FormExample() {
  const [name, setName] = useState("");
  const [age, setAge] = useState("");

  return (
    <div>
      <input
        placeholder="Enter name"
        value={name}
        onChange={(e) => setName(e.target.value)}
      />
      <input
        placeholder="Enter age"
        value={age}
        onChange={(e) => setAge(e.target.value)}
      />
      <p>
        Hi {name}, you are {age} years old.
      </p>
    </div>
  );
}
```

✅ Try typing — React will instantly re-render the paragraph with your input.

---

## ⏱️ The `useEffect` Hook

`useEffect` lets you **run code after rendering** — for example:

* fetching data from an API
* setting up subscriptions
* updating the document title

---

### Example 1: Log When the Component Renders

```jsx
import { useEffect } from "react";

function Welcome() {
  useEffect(() => {
    console.log("Component has rendered!");
  });
  
  return <h1>Welcome to React 🚀</h1>;
}
```

💡 This runs **after every render** by default.

---

### Example 2: Run Once (on Mount)

If you pass an empty dependency array `[]`, it runs **only once** (like `componentDidMount` in class components).

```jsx
useEffect(() => {
  console.log("Component mounted once!");
}, []);
```

---

### Example 3: Watch for Specific Changes

If you add variables inside the array, it runs **whenever those variables change.**

```jsx
useEffect(() => {
  console.log(`Count changed: ${count}`);
}, [count]);
```

---

## 🌐 Example: Fetching Data

Here’s a real-world useEffect example:

```jsx
import { useState, useEffect } from "react";

function UsersList() {
  const [users, setUsers] = useState([]);

  useEffect(() => {
    fetch("https://jsonplaceholder.typicode.com/users")
      .then((res) => res.json())
      .then((data) => setUsers(data));
  }, []); // runs once

  return (
    <div>
      <h2>Users</h2>
      <ul>
        {users.map((user) => (
          <li key={user.id}>{user.name}</li>
        ))}
      </ul>
    </div>
  );
}
```

✅ This will display a list of users fetched from a public API.

---

## ⚙️ Combining State + useEffect

Let’s mix both concepts:

```jsx
import { useState, useEffect } from "react";

function Timer() {
  const [seconds, setSeconds] = useState(0);

  useEffect(() => {
    const interval = setInterval(() => {
      setSeconds((prev) => prev + 1);
    }, 1000);

    return () => clearInterval(interval); // cleanup
  }, []);

  return <h2>Timer: {seconds}s</h2>;
}
```

✅ `setInterval` runs every second.
✅ The cleanup function (`return () => clearInterval(interval)`) stops it when the component unmounts.

---

## 🧪 Challenge #3

🎯 **Task:**

1. Create a new component `ColorChanger.js`.
2. Add a button that randomly changes the background color when clicked.

Hint:

```jsx
const colors = ["red", "green", "blue", "purple", "orange"];
const randomColor = colors[Math.floor(Math.random() * colors.length)];
```

Use `useState` to store the color.

---

## 💡 Key Takeaways

| Concept       | Description                                |
| ------------- | ------------------------------------------ |
| **State**     | Tracks changing data inside components     |
| **useState**  | React Hook to manage local state           |
| **useEffect** | Runs side effects like fetching data       |
| **Cleanup**   | Prevents memory leaks or unwanted behavior |

---

## 🧠 Bonus Challenge

Build a **Quote Generator** app:

* Use `useState` to hold a quote.
* Use `useEffect` to fetch a random quote from an API (e.g. `https://api.quotable.io/random`).
* Show a button to fetch a new one.

---

> ⚡ **Pro Tip:**
> Every time data changes — state changes.
> Every time something happens outside React (like API calls), use `useEffect`.

```

---

✅ Now you have a complete **Week 1 module**:
1. Introduction to React  
2. Components and Props  
3. State and useEffect  

```
