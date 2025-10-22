Perfect 🚀
Here’s your **Week 2, Lesson 1** file —
📘 `week-02-react-routing-and-forms/lessons/01-react-router-basics.md`

---

## **01-react-router-basics.md**

````markdown
# Lesson 1: React Router Basics

---

## 🧭 What is React Router?

In React, we often build **Single Page Applications (SPAs)** — meaning:
- The app runs on **one HTML page** (`index.html`)
- React dynamically changes what’s displayed without reloading the page.

**React Router** helps us handle **navigation** between different views (or pages) in a React app — e.g. Home, About, Contact, Dashboard.

---

## ⚙️ Installing React Router

Run this in your project terminal:

```bash
npm install react-router-dom
````

or

```bash
yarn add react-router-dom
```

✅ This gives you access to all the tools needed for navigation in React.

---

## 🏗️ Setting Up the Router

In your main file (`index.js` or `main.jsx`), wrap your app inside a `<BrowserRouter>`:

```jsx
import { createRoot } from "react-dom/client";
import { BrowserRouter } from "react-router-dom";
import App from "./App";

const root = createRoot(document.getElementById("root"));
root.render(
  <BrowserRouter>
    <App />
  </BrowserRouter>
);
```

This tells React:

> “Hey, I want to handle navigation inside this app using React Router.”

---

## 🧩 Defining Routes

In your `App.js`, you’ll use `<Routes>` and `<Route>` to define which components show for each URL path.

Example:

```jsx
import { Routes, Route } from "react-router-dom";
import Home from "./pages/Home";
import About from "./pages/About";
import Contact from "./pages/Contact";

function App() {
  return (
    <div>
      <Routes>
        <Route path="/" element={<Home />} />
        <Route path="/about" element={<About />} />
        <Route path="/contact" element={<Contact />} />
      </Routes>
    </div>
  );
}

export default App;
```

✅ Each `<Route>` maps a **path** to a **component**.

---

## 📄 Creating the Pages

Create a `pages/` folder with three simple files:

```jsx
// pages/Home.jsx
export default function Home() {
  return <h1>🏠 Welcome Home</h1>;
}

// pages/About.jsx
export default function About() {
  return <h1>ℹ️ About This App</h1>;
}

// pages/Contact.jsx
export default function Contact() {
  return <h1>📞 Contact Us</h1>;
}
```

---

## 🧭 Adding Navigation Links

You can move between pages without refreshing using the `<Link>` component.

```jsx
import { Link } from "react-router-dom";

function Navbar() {
  return (
    <nav style={{ display: "flex", gap: "1rem" }}>
      <Link to="/">Home</Link>
      <Link to="/about">About</Link>
      <Link to="/contact">Contact</Link>
    </nav>
  );
}

export default Navbar;
```

Now include the Navbar in your `App.js`:

```jsx
import Navbar from "./components/Navbar";

function App() {
  return (
    <>
      <Navbar />
      <Routes>
        {/* your routes */}
      </Routes>
    </>
  );
}
```

✅ Clicking links will switch pages *instantly* — without reloading.

---

## ⚡ Route Parameters

Sometimes you need **dynamic URLs** — e.g. `/user/1`, `/user/2`, etc.

You can define routes with parameters:

```jsx
<Route path="/user/:id" element={<User />} />
```

And access the parameter using the `useParams()` hook:

```jsx
import { useParams } from "react-router-dom";

function User() {
  const { id } = useParams();
  return <h2>User ID: {id}</h2>;
}
```

✅ Visiting `/user/5` will display “User ID: 5”.

---

## 🔁 Navigate Programmatically

You can also navigate with code using the `useNavigate()` hook.

```jsx
import { useNavigate } from "react-router-dom";

function Login() {
  const navigate = useNavigate();

  function handleLogin() {
    // After login success
    navigate("/dashboard");
  }

  return <button onClick={handleLogin}>Login</button>;
}
```

✅ Clicking the button will send you to `/dashboard`.

---

## 🧱 Nested Routes

You can nest routes inside each other for layouts like dashboards.

```jsx
<Route path="/dashboard" element={<DashboardLayout />}>
  <Route path="home" element={<DashboardHome />} />
  <Route path="settings" element={<Settings />} />
</Route>
```

Then in `DashboardLayout.js`:

```jsx
import { Outlet, Link } from "react-router-dom";

function DashboardLayout() {
  return (
    <div>
      <nav>
        <Link to="home">Home</Link>
        <Link to="settings">Settings</Link>
      </nav>
      <Outlet /> {/* Nested page renders here */}
    </div>
  );
}

export default DashboardLayout;
```

---

## 🧪 Challenge #1

🎯 **Task:**

1. Create a small app with three pages: `Home`, `Services`, and `Contact`.
2. Add navigation links for each.
3. Add one dynamic route: `/service/:id` that displays “Service ID: {id}”.
4. Try navigating to `/service/101`.

---

## 💡 Key Takeaways

| Concept                | Description                            |
| ---------------------- | -------------------------------------- |
| **React Router**       | Handles client-side navigation         |
| **<BrowserRouter>**    | Wraps your app for routing             |
| **<Route> & <Routes>** | Define the page paths                  |
| **<Link>**             | Navigate between pages without refresh |
| **useParams()**        | Access route parameters                |
| **useNavigate()**      | Navigate programmatically              |

---

## 🧠 Bonus Challenge

Add an **active link style** to the navbar:

* Use `NavLink` instead of `Link`
* Apply a different color for the active page

Example:

```jsx
import { NavLink } from "react-router-dom";

<NavLink
  to="/about"
  style={({ isActive }) => ({
    color: isActive ? "blue" : "gray",
  })}
>
  About
</NavLink>
```

---

> 💬 **Pro Tip:**
> Think of React Router as your app’s “GPS” — it decides what to display depending on your route, without ever leaving the page.

```

---

Would you like me to continue with **Lesson 2 — Building Forms in React (`02-building-forms-in-react.md`)** next?
```
