# 🏅 Sporting Goods Store — Team Syntax

> CSC 490: Software Engineering
> Dr. Ramzi Haraty — Lebanese American University

![React](https://img.shields.io/badge/React-19-blue)
![TypeScript](https://img.shields.io/badge/TypeScript-5.0-3178C6)
![Firebase](https://img.shields.io/badge/Firebase-Backend-orange)
![Vite](https://img.shields.io/badge/Vite-Build_Tool-646CFF)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)
![License](https://img.shields.io/badge/License-Academic-lightgrey)

---

## 👥 Team Members

| Name | Student ID | Role |
|------|------------|------|
| Jawad Jradi | 202306322 | Authentication, Routing, Reviews UI |
| Mustafa Kassem Hammoud | 202308271 | Product Catalog, Admin Products UI |
| Dani Hmaidan | 202405448 | Cart, Checkout, Filters, Product Detail |
| Kassem Nader | 202300068 | Admin Dashboard, Orders, Inventory |

---

## 🌐 Live Demo

🔗 **https://sporting-goods-30f8b.web.app**

> The application is fully deployed and accessible. No installation required to view the live version.

---

## 📋 Project Description

A modern, full-stack web-based e-commerce platform for a Sporting Goods Store, developed as part of CSC 490: Software Engineering at the Lebanese American University.

The system provides two distinct interfaces:
- **Customer (Buyer):** Browse, search, filter, and purchase sporting products across multiple sports and equipment categories.
- **Administrator:** Manage the full product catalog, monitor inventory, process orders, and moderate customer reviews through a centralized admin panel.

The application uses Firebase as its backend, handling authentication, real-time database operations, file storage, and hosting — eliminating the need for a traditional server. All transactions are processed via Cash on Delivery (COD) or order confirmation, as per the project requirements.

---

## 🛠️ Tech Stack

| Layer | Technology | Purpose |
|-------|------------|---------|
| Frontend Framework | React 19 + TypeScript | Component-based UI with type safety |
| Build Tool | Vite | Fast development server and bundler |
| Styling | CSS Modules + Framer Motion | Responsive design and animations |
| Authentication | Firebase Auth | Email/password and Google sign-in |
| Database | Firebase Firestore | Real-time NoSQL document database |
| File Storage | Firebase Storage | Product image uploads |
| Hosting | Firebase Hosting | Production deployment |
| Icons | Lucide React, React Icons | UI iconography |
| Routing | React Router DOM v7 | Client-side navigation |

---

## ✅ Implemented Features

### 🛒 Customer (Buyer)
- Register and log in via Email/Password or Google
- Browse products by sport (Running, Basketball, Football, Tennis, Swimming, Training)
- Filter by category (Shoes, Apparel, Equipment, Accessories)
- Filter by price range
- Search products by name, brand, or description
- Sort products by name, price, or rating
- View detailed product pages with images, ratings, and reviews
- Submit product reviews with star ratings
- Add products to cart, update quantities, remove items
- Checkout with full shipping address form
- Automatic stock reduction on order placement
- View complete order history with status tracking
- Manage user profile (display name, account info)

### 🛠️ Administrator
- Dashboard with real-time statistics: total products, active orders, revenue, low-stock alerts
- Add new products (name, description, price, images, sport, category, brand, stock)
- Edit and delete existing products
- Manage sports and equipment categories (add, edit, delete)
- View all customer orders with buyer details
- Update order status: Pending → Processing → Completed / Cancelled
- Inventory management with low-stock threshold warnings
- Inventory logs tracking every stock change event
- View and delete customer reviews (moderation)

---

## 📁 Project Structure

```
sporting-goods-store/
├── public/                  # Static assets (favicon, icons)
├── src/
│   ├── assets/              # Images and static files
│   ├── components/
│   │   ├── Navbar/          # Navigation bar with cart badge and auth state
│   │   ├── Footer/          # Site footer
│   │   ├── HeroBackground/  # Animated 3D hero section
│   │   └── ProtectedRoute   # Route guard for auth and admin access
│   ├── context/
│   │   ├── AuthContext.tsx  # Firebase auth state, login, register, Google sign-in
│   │   └── CartContext.tsx  # Cart state management (add, update, remove, total)
│   ├── pages/
│   │   ├── Home/            # Landing page with featured products and sports grid
│   │   ├── Products/        # Product listing with filters + product detail page
│   │   ├── Cart/            # Shopping cart page
│   │   ├── Checkout/        # Checkout form and order placement
│   │   ├── Orders/          # Order history for buyers
│   │   ├── Profile/         # User profile management
│   │   ├── Auth/            # Login and registration pages
│   │   └── Admin/           # Full admin panel (dashboard, products, orders, inventory, reviews)
│   ├── config/
│   │   └── firebase.ts      # Firebase app initialization and service exports
│   ├── types/
│   │   └── index.ts         # TypeScript interfaces (User, Product, Order, Review, etc.)
│   ├── styles/
│   │   └── globals.css      # Global CSS variables and shared styles
│   ├── App.tsx              # Root component with routing configuration
│   └── main.tsx             # Application entry point
├── database/
│   └── SEED_DATA.md         # Sample product data for initial setup
├── firestore.rules          # Firestore security rules (RBAC)
├── firestore.indexes.json   # Composite Firestore indexes
├── firebase.json            # Firebase hosting configuration
├── vite.config.ts           # Vite build configuration
├── tsconfig.json            # TypeScript configuration
└── package.json             # Project dependencies and scripts
```

---

## 🚀 Setup Instructions

### Prerequisites

- Node.js v18 or higher
- npm v9 or higher
- A modern web browser

### Installation

```bash
# 1. Clone the repository
git clone https://github.com/jawadjradi/sporting-goods-store.git

# 2. Navigate into the project directory
cd sporting-goods-store

# 3. Install dependencies
npm install

# 4. Start the development server
npm run dev
```

Open **http://localhost:5173** in your browser.

### Build for Production

```bash
npm run build
```

### Deploy to Firebase Hosting

```bash
npm run build
firebase deploy
```

---

## ▶️ Usage Guide

### Customer Flow
1. Visit the live site or run locally
2. Click **Sign In** → Register a new account or continue with Google
3. Browse the homepage or click **Products** to explore the full catalog
4. Use the sidebar filters to narrow by sport, category, or price
5. Click any product to view its detail page
6. Click **Add to Cart** → review your cart → proceed to **Checkout**
7. Fill in your shipping address → click **Place Order**
8. View your order under **Orders** in the navbar

### Admin Flow
1. Log in with an admin account (see Admin Access below)
2. Click **Admin** in the navbar to access the admin panel
3. Use the sidebar to navigate: Dashboard / Products / Orders / Inventory / Categories / Reviews
4. Add or edit products using the product form
5. Update order statuses from the Orders panel
6. Monitor and adjust stock levels from the Inventory panel
7. Delete inappropriate reviews from the Reviews panel

---

## 🔑 Admin Access

To grant admin privileges to a user:

1. Go to [Firebase Console](https://console.firebase.google.com)
2. Select project **sporting-goods-30f8b**
3. Navigate to **Firestore Database → users collection**
4. Find the user document by their email
5. Edit the `role` field: change `"customer"` → `"admin"`
6. Log out and back in on the site — the Admin link will appear in the navbar

---

## 🔒 Security

Firestore Security Rules enforce role-based access control (RBAC):

| Collection | Public Read | Authenticated Write | Admin Only |
|------------|-------------|----------------------|------------|
| products | ✅ | ❌ | ✅ |
| orders | ❌ | ✅ (own) | ✅ (all) |
| reviews | ✅ | ✅ (create) | ✅ (delete) |
| users | ❌ | ✅ (own) | ✅ |
| inventoryLogs | ❌ | ❌ | ✅ |
| taxonomies | ✅ | ❌ | ✅ |

---

## 📄 Project Phases

| Phase | Title | Description |
|-------|-------|-------------|
| Phase I | Requirements & Architecture | User requirements, system architecture, glossary |
| Phase II | System Models & Design | Use case diagrams, activity diagrams, ERD, database schema |
| Phase III | Test Cases | Functional and non-functional test cases |
| Phase IV | Implementation | Full system implementation (this repository) |

---

## 🔗 Links

- **Live Application:** https://sporting-goods-30f8b.web.app
- **GitHub Repository:** https://github.com/jawadjradi/sporting-goods-store
- **Course:** CSC 490 — Software Engineering, Lebanese American University
