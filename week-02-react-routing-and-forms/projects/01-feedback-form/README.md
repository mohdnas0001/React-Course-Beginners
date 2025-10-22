**`week-02-react-routing-and-forms/projects/01-feedback-form/`**

---

### 📁 Folder Structure

```
01-feedback-form/
│
├── README.md
└── src/
    ├── App.jsx
    ├── components/
    │   ├── FeedbackForm.jsx
    │   └── FeedbackList.jsx
    └── index.js
```

---

### 🧾 **README.md**

````md
# 📝 Feedback Form App

A simple React app to practice handling **forms**, **events**, and **state**.

---

## 🎯 Objectives
- Learn how to handle user inputs with `useState`
- Practice form submission with `onSubmit`
- Dynamically display a list of submitted feedbacks

---

## 🧩 Features
- Input fields for **name** and **message**
- Submit button to add feedback
- Display submitted feedback below the form

---

## 🚀 How to Run
```bash
# Navigate to the project
cd week-02-react-interactivity/projects/01-feedback-form

# Create React app (if not created yet)
npx create-react-app .

# Start the app
npm start
````

---

## 📂 Components

### 1️⃣ `FeedbackForm.jsx`

Handles the form logic.

### 2️⃣ `FeedbackList.jsx`

Displays the feedback entries.

````

---

### ⚛️ **FeedbackForm.jsx**
```jsx
import { useState } from "react";

export default function FeedbackForm({ onAddFeedback }) {
  const [form, setForm] = useState({ name: "", message: "" });

  function handleChange(e) {
    setForm({ ...form, [e.target.name]: e.target.value });
  }

  function handleSubmit(e) {
    e.preventDefault();
    if (!form.name || !form.message) return alert("Please fill all fields!");

    onAddFeedback(form);
    setForm({ name: "", message: "" }); // reset form
  }

  return (
    <form onSubmit={handleSubmit} className="feedback-form">
      <input
        type="text"
        name="name"
        placeholder="Your name"
        value={form.name}
        onChange={handleChange}
      />
      <textarea
        name="message"
        placeholder="Your feedback..."
        value={form.message}
        onChange={handleChange}
      />
      <button type="submit">Submit Feedback</button>
    </form>
  );
}
````

---

### ⚛️ **FeedbackList.jsx**

```jsx
export default function FeedbackList({ feedbacks }) {
  if (feedbacks.length === 0) return <p>No feedback yet.</p>;

  return (
    <ul>
      {feedbacks.map((fb, index) => (
        <li key={index}>
          <strong>{fb.name}</strong>: {fb.message}
        </li>
      ))}
    </ul>
  );
}
```

---

### ⚛️ **App.jsx**

```jsx
import { useState } from "react";
import FeedbackForm from "./components/FeedbackForm";
import FeedbackList from "./components/FeedbackList";

export default function App() {
  const [feedbacks, setFeedbacks] = useState([]);

  function handleAddFeedback(newFeedback) {
    setFeedbacks([newFeedback, ...feedbacks]);
  }

  return (
    <div className="App">
      <h1>Feedback Form</h1>
      <FeedbackForm onAddFeedback={handleAddFeedback} />
      <FeedbackList feedbacks={feedbacks} />
    </div>
  );
}
```

---

### ⚙️ **index.js**

```jsx
import React from "react";
import ReactDOM from "react-dom/client";
import App from "./App";
import "./index.css";

const root = ReactDOM.createRoot(document.getElementById("root"));
root.render(<App />);
```

---

Would you like me to include a **simple CSS file (`index.css`)** next to make the layout clean and beginner-friendly?
