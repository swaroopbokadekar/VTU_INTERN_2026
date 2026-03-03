Here is your **well-formatted plain text document** that you can directly share with students (Notepad / PDF / LMS ready).

---

# Introduction to React

## 1. What is React?

React is a **web application framework (JavaScript library)** used for designing and developing the **User Interface (UI) or Frontend** of web applications.

It is mainly used to build **interactive and dynamic web applications**.

---

## 2. Core Concepts of React

### 🔹 Virtual DOM

React is based on the **Virtual DOM** concept.

* Instead of updating the entire real DOM,
* React updates a virtual copy in memory,
* Then efficiently updates only the changed parts in the real DOM.

This makes React applications **fast and efficient**.

---

### 🔹 JSX (JavaScript XML)

React uses **JSX**.

JSX combines the power of:

* JavaScript
* HTML-like syntax

File extension: `.jsx`

JSX is called JSX because:

* The elements are not pure HTML.
* They are JavaScript-based XML-like structures.
* Example: `className` is used instead of `class`.

Example:

```jsx
const element = <h1>Hello Students</h1>;
```

---

## 3. SPA – Single Page Application

A React application contains **only one HTML file**.

That file is:

```
index.html
```

Because it uses only one HTML file, it is called a:

👉 **SPA (Single Page Application)**

Even though:

* The page is made up of multiple components,
* The end user does not feel page reloads,
* It feels smooth compared to traditional multiple HTML page websites.

---

# Creating a React Application

## Step 1: Create App

```bash
npm create vite@latest my-app
```

This command:

* Creates a new React project
* Generates required folders such as:

  * node_modules
  * src
  * public
  * package.json
  * etc.

---

# How Does a React Application Work?

## 1. Entry Point – main.jsx

Inside the `src` folder, we have:

```
main.jsx
```

This file:

* Loads the root component
* Connects React to `index.html`

---

## 2. index.html

This is the **only HTML file** in the entire application.

It contains:

```html
<div id="root"></div>
```

React injects all components inside this `root` div.

---

## 3. Root Component – App.jsx

The root component is:

```
App.jsx
```

* It is automatically created when we create the React app.
* It acts as the main parent component.
* Other components are placed inside App.

---

## 4. CSS Structure

Each component can have its own CSS file.

Example:

* App.jsx → App.css
* StudDashboard.jsx → StudDashboard.css

Additionally:

```
index.css
```

This file:

* Applies global styles
* Affects the entire application

---

# Components in React

React applications are built using **Components**.

A component is a reusable piece of UI.

---

## Types of Components

1. Class Components (Old approach)
2. Functional Components (Modern approach)

👉 Today, we mostly use **Functional Components**.

---

# Creating a Functional Component

## Step 1: Create a JSX File

Example:

```
StudDashboard.jsx
```

---

## Step 2: Use RFCE Snippet

Install Extension:

**ES7 React/Redux/GraphQL/React-Native Snippets**

Then type:

```
rfce
```

This automatically generates boilerplate code.

---

## Example: Functional Component

```jsx
import React from 'react'

function LecturerDashboard() {
  return (
    <div>
      
    </div>
  )
}

export default LecturerDashboard
```

Explanation:

* `function LecturerDashboard()` → Component definition
* `return()` → JSX to display UI
* `export default` → Makes component usable in other files

---

# Summary for Discussion

You can ask students:

* Why is Virtual DOM faster?
* Why do we call React an SPA?
* What is the difference between index.css and component CSS?
* Why are functional components preferred today?
* What happens if we remove main.jsx?

---

If you want, I can also prepare:

* A diagram-based explanation of React flow
* A 1-hour classroom discussion plan
* A small demo plan aligned with this theory
* Interview-focused React basics notes
* Comparison: React vs Traditional HTML

Just tell me your teaching goal 😊
