### 📘 **Lesson 02: Handling Forms and Events**

---

### 🧠 **Overview**

React makes it easy to handle user interactions through **events** and **controlled components**.
This lesson will teach you how to:

* Handle user input events (clicks, typing, submission, etc.)
* Manage form data with React’s **state**
* Understand **controlled** vs **uncontrolled** components

---

### 🎯 **1. Event Handling in React**

React uses a camelCase syntax for events (e.g., `onClick`, `onChange`).

Example:

```jsx
function ClickExample() {
  function handleClick() {
    alert("Button was clicked!");
  }

  return <button onClick={handleClick}>Click Me</button>;
}
```

> 💡 Unlike vanilla JS, you don’t use `addEventListener()` — React binds events directly in JSX.

---

### 🎨 **2. Handling Input Fields**

Use the **onChange** event to track what the user types.

```jsx
import { useState } from "react";

function InputExample() {
  const [name, setName] = useState("");

  function handleChange(e) {
    setName(e.target.value);
  }

  return (
    <div>
      <input type="text" value={name} onChange={handleChange} placeholder="Enter your name" />
      <p>Hello, {name}!</p>
    </div>
  );
}
```

> 🧩 Here, the input is **controlled** by React — its value is managed through `useState`.

---

### 🧾 **3. Handling Form Submission**

Forms in React don’t refresh the page by default when handled properly.

```jsx
import { useState } from "react";

function FormExample() {
  const [email, setEmail] = useState("");

  function handleSubmit(e) {
    e.preventDefault();
    alert(`Submitted email: ${email}`);
  }

  return (
    <form onSubmit={handleSubmit}>
      <input
        type="email"
        value={email}
        placeholder="Enter your email"
        onChange={(e) => setEmail(e.target.value)}
      />
      <button type="submit">Submit</button>
    </form>
  );
}
```

> ✅ Always use `e.preventDefault()` to stop the form from reloading the page.

---

### ⚖️ **4. Controlled vs Uncontrolled Inputs**

| Type             | Managed By  | Example                           |
| ---------------- | ----------- | --------------------------------- |
| **Controlled**   | React State | `value={state}` + `onChange`      |
| **Uncontrolled** | DOM         | Using `ref` to access input value |

Controlled example (React-way):

```jsx
<input value={name} onChange={(e) => setName(e.target.value)} />
```

Uncontrolled example (DOM-way):

```jsx
import { useRef } from "react";

function UncontrolledInput() {
  const inputRef = useRef(null);

  function handleSubmit() {
    alert(inputRef.current.value);
  }

  return (
    <div>
      <input ref={inputRef} type="text" placeholder="Type something" />
      <button onClick={handleSubmit}>Show Value</button>
    </div>
  );
}
```

---

### 🧩 **5. Multiple Inputs**

For larger forms, it’s common to store all values in a single state object.

```jsx
import { useState } from "react";

function SignupForm() {
  const [formData, setFormData] = useState({ name: "", email: "" });

  function handleChange(e) {
    setFormData({ ...formData, [e.target.name]: e.target.value });
  }

  function handleSubmit(e) {
    e.preventDefault();
    console.log(formData);
  }

  return (
    <form onSubmit={handleSubmit}>
      <input
        name="name"
        value={formData.name}
        onChange={handleChange}
        placeholder="Name"
      />
      <input
        name="email"
        value={formData.email}
        onChange={handleChange}
        placeholder="Email"
      />
      <button type="submit">Submit</button>
    </form>
  );
}
```

---

### 💡 **6. Quick Practice**

✅ Create a simple login form with email and password fields.
✅ Show an alert when the user submits, displaying both values.
✅ Make sure both inputs are **controlled**.

---

### 🧭 **Next Lesson:** Conditional Rendering

---

Would you like me to generate the **practice project folder** for this week next (e.g., `feedback-form` mini app)?
