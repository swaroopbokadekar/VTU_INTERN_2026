Perfect 👍 Since you already ran:

```bash
npm create vite@latest stud_mngt
```

Let’s now align everything properly for a **clean, professional setup** (without recreating package.json or vite.config.js manually).

---

# ✅ Step 1: Enter the Project

```bash
cd stud_mngt
npm install
npm install react-router-dom
npm run dev
```

Now we will **modify only the src folder**.

---

# 🏗️ Final Project Structure (Inside src)

After cleanup, your structure should look like this:

```
stud_mngt
│
├── public
│
├── src
│   ├── components
│   │     ├── Navbar.jsx
│   │     ├── Footer.jsx
│   │
│   ├── layouts
│   │     ├── MainLayout.jsx
│   │
│   ├── pages
│   │     ├── Home.jsx
│   │     ├── Login.jsx
│   │     ├── Register.jsx
│   │
│   ├── App.jsx
│   ├── main.jsx
│   └── index.css
│
├── index.html
├── vite.config.js
└── package.json
```

---

# 🔥 Important: Clean Default Files

Delete:

```
App.css
assets/
```

We’ll use `index.css` only.

---

# ✅ Update main.jsx (Very Important)

📁 `src/main.jsx`

```jsx
import React from "react";
import ReactDOM from "react-dom/client";
import { BrowserRouter } from "react-router-dom";
import App from "./App";
import "./index.css";

ReactDOM.createRoot(document.getElementById("root")).render(
  <React.StrictMode>
    <BrowserRouter>
      <App />
    </BrowserRouter>
  </React.StrictMode>
);
```

---

# ✅ Update App.jsx

Replace the default Vite content completely.

📁 `src/App.jsx`

```jsx
import { Routes, Route } from "react-router-dom";
import MainLayout from "./layouts/MainLayout";
import Home from "./pages/Home";
import Login from "./pages/Login";
import Register from "./pages/Register";

function App() {
  return (
    <MainLayout>
      <Routes>
        <Route path="/" element={<Home />} />
        <Route path="/login" element={<Login />} />
        <Route path="/register" element={<Register />} />
      </Routes>
    </MainLayout>
  );
}

export default App;
```

---

# ✅ Create Required Folders

Inside `src`, create:

* components
* layouts
* pages

---

# ✅ components/Navbar.jsx

```jsx
import { Link } from "react-router-dom";

function Navbar() {
  return (
    <nav className="navbar">
      <h2>Stud_Mngt</h2>

      <div>
        <Link to="/">Home</Link>
        <Link to="/login">Login</Link>
        <Link to="/register">Register</Link>
      </div>
    </nav>
  );
}

export default Navbar;
```

---

# ✅ components/Footer.jsx

```jsx
function Footer() {
  return (
    <footer className="footer">
      <p>© 2026 Student Management System</p>
      <p>Powered by React + Vite</p>
    </footer>
  );
}

export default Footer;
```

---

# ✅ layouts/MainLayout.jsx

```jsx
import Navbar from "../components/Navbar";
import Footer from "../components/Footer";

function MainLayout({ children }) {
  return (
    <>
      <Navbar />
      <div style={{ minHeight: "80vh" }}>
        {children}
      </div>
      <Footer />
    </>
  );
}

export default MainLayout;
```

---

# ✅ pages/Home.jsx

```jsx
function Home() {
  return (
    <div className="container">
      <h1>Welcome to Student Management System</h1>
      <p>Manage students, courses, and reports efficiently.</p>

      <div className="card-section">
        <div className="card">
          <h3>Students</h3>
          <p>Maintain student records.</p>
        </div>

        <div className="card">
          <h3>Courses</h3>
          <p>Assign and track courses.</p>
        </div>

        <div className="card">
          <h3>Reports</h3>
          <p>Generate academic reports.</p>
        </div>
      </div>
    </div>
  );
}

export default Home;
```

---

# ✅ pages/Login.jsx

```jsx
function Login() {
  return (
    <div className="container">
      <h2>Login</h2>

      <form className="form">
        <input type="text" placeholder="Username" />
        <input type="password" placeholder="Password" />
        <button type="submit">Login</button>
      </form>
    </div>
  );
}

export default Login;
```

---

# ✅ pages/Register.jsx

```jsx
function Register() {
  return (
    <div className="container">
      <h2>Register</h2>

      <form className="form">
        <input type="text" placeholder="Full Name" />
        <input type="email" placeholder="Email" />
        <input type="password" placeholder="Password" />
        <button type="submit">Register</button>
      </form>
    </div>
  );
}

export default Register;
```

---

# ✅ index.css

Replace entire file:

```css
body {
  margin: 0;
  font-family: Arial, sans-serif;
  background-color: #f1f5f9;
}

.navbar {
  display: flex;
  justify-content: space-between;
  padding: 15px 40px;
  background-color: #1e293b;
  color: white;
}

.navbar a {
  color: white;
  text-decoration: none;
  margin-left: 20px;
}

.footer {
  background-color: #0f172a;
  color: white;
  text-align: center;
  padding: 20px;
}

.container {
  padding: 60px;
  text-align: center;
}

.card-section {
  display: flex;
  justify-content: center;
  gap: 20px;
  margin-top: 40px;
}

.card {
  background: white;
  padding: 20px;
  width: 250px;
  border-radius: 8px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}

.form {
  display: flex;
  flex-direction: column;
  width: 300px;
  margin: auto;
}

.form input {
  padding: 10px;
  margin: 10px 0;
}

.form button {
  padding: 10px;
  background-color: #2563eb;
  color: white;
  border: none;
  cursor: pointer;
}
```

---

# 🚀 Now Run

```bash
npm run dev
```

---

# 🎯 What You’ve Achieved

✔ Vite-based React app
✔ Proper folder architecture
✔ Routing
✔ Layout pattern
✔ Clean reusable components
✔ Home, Login, Register pages

