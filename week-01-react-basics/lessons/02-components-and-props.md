`week-01-react-basics/lessons/02-components-and-props.md`

---

## 📘 **02-components-and-props.md**

````markdown
# Lesson 2: Components and Props

---

## 🧩 What Are Components?

A **component** in React is like a reusable building block.  
You can think of it as a *function* that returns HTML-like syntax called **JSX**.

There are two main types of components:
1. **Functional Components** — the modern way (what we’ll use)
2. **Class Components** — older and less common now

Example:

```jsx
function Greeting() {
  return <h1>Hello, React Learner 👋🏽</h1>;
}
````

---

## 🔁 Reusability in Components

You can reuse the same component multiple times in your app.

```jsx
function App() {
  return (
    <div>
      <Greeting />
      <Greeting />
      <Greeting />
    </div>
  );
}
```

React will render three greetings — simple, right?
That’s the power of reusable components.

---

## 🧳 Passing Data with Props

**Props** (short for *properties*) allow you to pass data into components.

Let’s modify our `Greeting` component:

```jsx
function Greeting(props) {
  return <h1>Hello, {props.name} 👋🏽</h1>;
}
```

Now you can reuse it with different names:

```jsx
function App() {
  return (
    <div>
      <Greeting name="Ada" />
      <Greeting name="Chinedu" />
      <Greeting name="Zainab" />
    </div>
  );
}
```

✅ Output:

```
Hello, Ada 👋🏽
Hello, Chinedu 👋🏽
Hello, Zainab 👋🏽
```

---

## 🎯 Destructuring Props

You can simplify the `props` syntax like this:

```jsx
function Greeting({ name }) {
  return <h1>Hello, {name} 👋🏽</h1>;
}
```

Same result, but cleaner code.
This is called **destructuring** — a common JavaScript pattern.

---

## 🧠 Real-World Example

Imagine a team of interns — you can represent each person as a **Card Component**.

```jsx
function InternCard({ name, role }) {
  return (
    <div style={{ border: "1px solid #ddd", padding: "1rem", borderRadius: "8px" }}>
      <h3>{name}</h3>
      <p>{role}</p>
    </div>
  );
}

function App() {
  return (
    <div>
      <InternCard name="Fatima Yusuf" role="Frontend Intern" />
      <InternCard name="Ifeanyi Ugo" role="Backend Intern" />
      <InternCard name="Grace Bello" role="UI/UX Intern" />
    </div>
  );
}
```

✅ Output:
Each card displays the name and role of an intern — all using reusable components.

---

## ⚙️ Component Organization

As your project grows, organize components in folders like this:

```
src/
 ├── App.js
 └── components/
      ├── Greeting.js
      └── InternCard.js
```

Then import them like so:

```jsx
import Greeting from "./components/Greeting";
import InternCard from "./components/InternCard";
```

---

## 🧪 Challenge #2

🎯 **Task:**

1. Create a new file in the `components` folder called `UserProfile.js`.
2. Add this code:

```jsx
function UserProfile({ name, email }) {
  return (
    <div style={{ padding: "1rem", border: "1px solid #ccc", borderRadius: "8px" }}>
      <h2>{name}</h2>
      <p>{email}</p>
    </div>
  );
}

export default UserProfile;
```

3. Import and use it inside `App.js` like this:

```jsx
import UserProfile from "./components/UserProfile";

function App() {
  return (
    <div>
      <UserProfile name="John Doe" email="john@example.com" />
      <UserProfile name="Jane Smith" email="jane@example.com" />
    </div>
  );
}
```

✅ Output:
Two user profiles displayed with their names and emails.

---

## 💡 Key Takeaways

| Concept           | Description                 |
| ----------------- | --------------------------- |
| **Component**     | A reusable piece of UI      |
| **Props**         | Data passed into components |
| **Destructuring** | Cleaner way to access props |
| **Reusability**   | Build once, use anywhere    |

---

## 🧠 Bonus Challenge

Create a component called `Button` that accepts two props:

* `label` — the text to display on the button
* `color` — the background color

Example:

```jsx
<Button label="Click Me" color="blue" />
```

Hint: You can apply inline styles using:

```jsx
style={{ backgroundColor: color }}
```

---

> 💬 **Pro Tip:**
> Always make your components small, focused, and reusable.
> It keeps your code cleaner and easier to maintain.

```

```
