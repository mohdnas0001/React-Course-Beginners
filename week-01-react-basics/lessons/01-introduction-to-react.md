Perfect 👌🏽 Let’s fill out your first lesson file:
`week-01-react-basics/lessons/01-introduction-to-react.md`

This content is **clean, practical, and written for interns** — explaining concepts clearly and including code examples + a mini challenge at the end.
You can paste this directly into your file.

---

## 📘 **01-introduction-to-react.md**

````markdown
# Lesson 1: Introduction to React

---

## 🧠 What is React?

React is a **JavaScript library** for building user interfaces.  
It helps you build **reusable components** — small pieces of UI that work together to create complex apps.

React was developed by **Facebook (now Meta)** and is now maintained by a large open-source community.

---

## 🚀 Why Learn React?

React makes it easy to:
- Build fast, interactive web applications.
- Reuse code with components.
- Manage UI updates efficiently with a **Virtual DOM**.
- Use the same concepts across **web, mobile (React Native)**, and even **desktop apps**.

---

## ⚙️ Setting Up Your Environment

Before starting, make sure you have:

| Tool | Purpose | Installation |
|------|----------|---------------|
| **Node.js** (v16 or higher) | Runs JavaScript outside the browser | [Download Here](https://nodejs.org) |
| **VS Code** | Your code editor | [Download Here](https://code.visualstudio.com) |
| **Yarn** or **npm** | Package manager | Installed automatically with Node.js |
| **Git** | Version control | [Download Here](https://git-scm.com) |

---

## 🧰 Creating Your First React App

Once everything is installed, open your terminal and run:

```bash
# Using npm
npx create-react-app my-first-react-app

# or using yarn
yarn create react-app my-first-react-app
````

Then navigate into your project:

```bash
cd my-first-react-app
yarn start
```

Your browser should automatically open [http://localhost:3000](http://localhost:3000) showing the React logo 🚀.

---

## 🗂 Folder Overview

Let’s understand the structure:

```
my-first-react-app/
├── node_modules/      # Dependencies
├── public/            # Static assets (favicon, index.html)
├── src/               # Where your React code lives
│   ├── App.js         # Main App component
│   ├── index.js       # Entry point of the app
│   └── components/    # Your custom components (you’ll create this later)
└── package.json       # Project metadata and dependencies
```

---

## ⚛️ Your First React Component

Open `src/App.js` and replace its contents with:

```jsx
function App() {
  return (
    <div>
      <h1>Hello React 👋🏽</h1>
      <p>Welcome to your first React app!</p>
    </div>
  );
}

export default App;
```

Then save the file.
You’ll instantly see the browser update — no refresh needed! ⚡

---

## 💡 Understanding the Code

| Concept              | Description                                             |
| -------------------- | ------------------------------------------------------- |
| **JSX**              | JavaScript + HTML syntax used in React.                 |
| **Component**        | A function that returns UI (JSX).                       |
| **`export default`** | Allows the component to be imported and used elsewhere. |

---

## 🧩 Challenge #1

🎯 **Task:**
Create a new file in the `src` folder called `Welcome.js`.

Inside it, write a new component:

```jsx
function Welcome() {
  return (
    <h2>Welcome to Week 1 of your React Internship 🚀</h2>
  );
}

export default Welcome;
```

Then import and use it in `App.js`:

```jsx
import Welcome from "./Welcome";

function App() {
  return (
    <div>
      <Welcome />
    </div>
  );
}
```

✅ When you see your “Welcome” message in the browser, congrats — you just built and composed your first React component!

---

## 📚 Summary

* React is a library for building UIs.
* Everything in React is a **component**.
* JSX combines JavaScript and HTML.
* You can start a React app using `create-react-app`.

---

## 🧪 Bonus Challenge

1. Add a new component called `Footer` that says:

   ```
   Built with ❤️ using React
   ```
2. Import it in `App.js` and display it below your welcome message.
3. Style it using inline CSS or Tailwind.

---

> 🧠 **Tip:** From now on, always think in *components*.
> Each part of your UI — navbar, button, footer — can be a small, reusable piece.

```

---

```
