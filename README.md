# 🍽️ TheMealDB Explorer

A responsive recipe browsing app built with React and Vite, powered by [TheMealDB](https://www.themealdb.com/) public API. Browse meals by category, search for specific dishes, and view detailed recipes with ingredients and video tutorials.

---

## ✨ Features

- **Browse by Category** — Explore meals organized by food categories (Beef, Chicken, Dessert, etc.)
- **Meal Detail Page** — View full recipe info including ingredients, measurements, instructions, and an embedded YouTube tutorial
- **Search Meals** — Search for any meal by name using the search bar
- **Responsive Design** — Works across mobile, tablet, and desktop
- **Client-side Routing** — Smooth navigation with React Router

---

## 🛠️ Tech Stack

| Tech | Purpose |
|------|---------|
| [React 19](https://react.dev/) | UI library |
| [Vite 8](https://vitejs.dev/) | Build tool & dev server |
| [React Router 7](https://reactrouter.com/) | Client-side routing |
| [Axios](https://axios-http.com/) | HTTP requests |
| [Tailwind CSS 4](https://tailwindcss.com/) | Utility-first styling |
| [shadcn/ui](https://ui.shadcn.com/) + [Radix UI](https://www.radix-ui.com/) | UI components |
| [Lucide React](https://lucide.dev/) | Icons |
| [TheMealDB API](https://www.themealdb.com/api.php) | Recipe data |

---

## 📁 Project Structure

```
src/
├── components/
│   ├── Header.jsx           # Top nav with logo and home link
│   ├── RootLayout.jsx       # Shared layout wrapper (Header + Outlet)
│   └── ui/
│       ├── card.jsx         # Reusable Card component (shadcn/ui)
│       └── input.jsx        # Reusable Input component (shadcn/ui)
├── config/
│   └── api.js               # Base API URL for TheMealDB
├── home/
│   └── Home.jsx             # Landing page with search and category grid
├── meals/
│   ├── CategoryMealList.jsx # Grid of meal categories
│   ├── MealList.jsx         # Meals filtered by category
│   ├── Meal.jsx             # Individual meal detail page
│   └── SearchMeal.jsx       # Search results page
├── not-found/
│   └── Notfound.jsx         # 404 page
├── lib/
│   └── utils.ts             # Tailwind class merge utility (cn)
├── App.jsx                  # Router setup
├── main.jsx                 # App entry point
└── index.css                # Global styles & Tailwind config
```

---

## 🚀 Getting Started

### Prerequisites

- [Node.js](https://nodejs.org/) v20 or higher
- npm v10 or higher

### Installation

1. **Clone the repository:**

   ```bash
   git clone https://github.com/your-username/mealdb-explorer.git
   cd mealdb-explorer
   ```

2. **Install dependencies:**

   ```bash
   npm install
   ```

3. **Start the development server:**

   ```bash
   npm run dev
   ```

   Open [http://localhost:5173](http://localhost:5173) in your browser.

---

## 📜 Available Scripts

| Script | Description |
|--------|-------------|
| `npm run dev` | Start the development server with HMR |
| `npm run build` | Build the app for production |
| `npm run preview` | Preview the production build locally |
| `npm run lint` | Run ESLint |

---

## 🌐 API Reference

All data is fetched from [TheMealDB free API](https://www.themealdb.com/api.php) (v1).

| Endpoint | Usage |
|----------|-------|
| `/categories.php` | Fetch all meal categories |
| `/filter.php?c={category}` | Fetch meals by category |
| `/lookup.php?i={id}` | Fetch a single meal by ID |
| `/search.php?s={name}` | Search meals by name |

The base URL is configured in `src/config/api.js`:

```js
export const baseUrl = "https://www.themealdb.com/api/json/v1/1/";
```

---

## 🗺️ Routes

| Path | Component | Description |
|------|-----------|-------------|
| `/` | `Home` | Landing page with category grid and search |
| `/meal-list/:category` | `MealList` | Meals filtered by category |
| `/meal/:id` | `Meal` | Full meal detail (ingredients, instructions, video) |
| `/search-meal?s=query` | `SearchMeal` | Search results |
| `*` | `Notfound` | 404 fallback page |

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).
