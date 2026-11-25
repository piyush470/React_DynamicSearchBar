# 🔍 Dynamic Search Bar with Debounce (React + Vite)

[![React](https://img.shields.io/badge/React-19.x-61DAFB?logo=react&logoColor=white)](https://react.dev/)
[![Vite](https://img.shields.io/badge/Vite-8.x-646CFF?logo=vite&logoColor=white)](https://vite.dev/)
[![API](https://img.shields.io/badge/API-DummyJSON-orange)](https://dummyjson.com)

A fast, responsive, and dynamic search bar built with **React 19** and **Vite**. This application queries the DummyJSON products API in real time as the user types, featuring a custom **debounce mechanism** using React hooks (`useRef`, `useEffect`) to optimize network requests and enhance performance.

> 🚀 **Learning Milestone:** Built as **Project #2** in my React learning journey to master hooks, asynchronous API calls, performance optimization (debouncing), and controlled components.

---

## ✨ Features

- **⚡ Live Dynamic Search**: Searches products in real time as the user inputs keywords.
- **⏱️ Custom Debouncing (300ms)**: Implements a delay mechanism using `useRef` and `setTimeout`/`clearTimeout` to avoid firing unnecessary API requests on every single keystroke.
- **🌐 Real-Time API Integration**: Fetches dynamic product data (thumbnails, titles, IDs) from the [DummyJSON Products API](https://dummyjson.com/products/search).
- **🎨 Clean & Minimalist UI**: Sleek, modern search interface with rounded search container, subtle shadows, and visual indicators (search icon, suggestion list, external link arrows).
- **📱 Responsive Layout**: Centered card design that adapts comfortably across different screen sizes.

---

## 🛠️ Tech Stack

- **Framework / Library**: [React 19](https://react.dev/)
- **Build Tool & Dev Server**: [Vite](https://vite.dev/)
- **Data Source**: [DummyJSON API](https://dummyjson.com/)
- **Styling**: Inline CSS / JavaScript Style Object (Modular CSS-in-JS pattern)
- **Language**: JavaScript (ES6+ / JSX)

---

## 🧠 Key React Concepts Applied

1. **`useState`**:
   - Manages the search input string (`query`).
   - Stores the fetched array of matching products (`data`).

2. **`useRef`**:
   - Holds the mutable `timerId` without causing unnecessary component re-renders when updated.

3. **`useEffect`**:
   - Watches changes in `query`.
   - Clears existing timeouts and schedules a new API fetch after a 300ms idle period (Debouncing pattern).

4. **Controlled Inputs & Event Handling**:
   - Synchronizes input value changes via `handleInputChange`.

5. **Conditional / Dynamic List Rendering**:
   - Maps through search results safely with unique `key={id}` and renders thumbnail images and titles.

---

## 📂 Project Structure

```text
dynamic-search-bar/
├── public/                 # Static assets
├── src/
│   ├── App.css             # Component-level styles
│   ├── App.jsx             # Main search component, debouncing, & API integration
│   ├── index.css           # Global styles
│   └── main.jsx            # React root mount (StrictMode)
├── index.html              # HTML entry point
├── package.json            # Project dependencies & scripts
├── vite.config.js          # Vite configuration
└── README.md               # Project documentation
```

---

## ⚙️ How It Works (Debouncing Logic)

When a user types into the search bar:
1. `handleInputChange` updates the `query` state.
2. The `useEffect` hook triggers on every `query` update:
   - If a previous timer is still running, it gets canceled with `clearTimeout(timerId.current)`.
   - A new timer is set for `300ms`.
3. If the user stops typing for 300ms, `getData()` executes:
   - Queries `https://dummyjson.com/products/search?q={query}`.
   - Populates the suggestions container with the matching products.

---

## 🚀 Getting Started

Follow these steps to run the project locally on your machine.

### Prerequisites

Make sure you have [Node.js](https://nodejs.org/) installed (v18+ recommended).

### Installation & Setup

1. **Clone the repository:**
   ```bash
   git clone https://github.com/piyush470/React_DynamicSearchBar.git
   cd React_DynamicSearchBar
   ```

2. **Install dependencies:**
   ```bash
   npm install
   ```

3. **Start the development server:**
   ```bash
   npm run dev
   ```

4. **Open in browser:**
   Open `http://localhost:5173` (or the port specified in your terminal) to explore the app.

---

## 📜 Available Scripts

In the project directory, you can run:

| Command | Description |
| :--- | :--- |
| `npm run dev` | Runs the app in development mode with Hot Module Replacement (HMR). |
| `npm run build` | Builds the app for production in the `dist` folder. |
| `npm run preview` | Locally previews the production build. |
| `npm run lint` | Runs ESLint to check for code issues. |

---

## 👨‍💻 Author

- **Piyush Raikwar**
- GitHub: [@piyush470](https://github.com/piyush470)

---

*Created with ❤️ as part of learning modern React development.*
