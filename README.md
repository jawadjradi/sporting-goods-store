# APEX Sporting Goods Store

APEX is a single-page ecommerce storefront built for a sporting goods catalogue. It covers the standard customer flow from browsing products to checkout, and it also includes a protected admin area for managing stock, orders, categories, and reviews.

The frontend is built with React, TypeScript, and Vite. Firebase is used for authentication, Firestore data storage, and file storage.

## Project Details

### What the app includes

- Product browsing with category and sport-based discovery
- Product detail pages
- Cart management with local persistence
- Email/password and Google sign-in
- Protected checkout, orders, and profile pages
- Admin dashboard with product, order, inventory, category, and review management
- Firestore-backed product and order data

### Stack

- React 19
- TypeScript
- Vite
- React Router
- Firebase Authentication
- Cloud Firestore
- Firebase Storage
- Framer Motion

### Main routes

- `/` - landing page and featured products
- `/products` - product listing
- `/products/:id` - product details
- `/cart` - shopping cart
- `/checkout` - protected checkout flow
- `/orders` - logged-in customer orders
- `/profile` - logged-in customer profile
- `/admin` - protected admin area

## Setup Instructions

### 1. Install dependencies

```bash
npm install
```

### 2. Start the development server

```bash
npm run dev
```

Vite will print a local development URL in the terminal, usually `http://localhost:5173`.

### 3. Build for production

```bash
npm run build
```

### 4. Preview the production build locally

```bash
npm run preview
```

### 5. Lint the codebase

```bash
npm run lint
```

## Firebase Setup

This project already contains a Firebase configuration in the source code, so it will connect to the configured Firebase project as-is.

If you want to point it at a different Firebase project:

1. Create a Firebase project.
2. Enable Authentication.
3. Enable Firestore Database.
4. Enable Storage if you plan to use uploaded product images.
5. Replace the config values in `src/config/firebase.ts` with your own project settings.

### Authentication providers

The app supports:

- Email and password sign-in
- Google sign-in

If you use a new Firebase project, make sure both providers are enabled in Firebase Authentication.

### Firestore data expected by the app

The app reads and writes to collections such as:

- `products`
- `orders`
- `users`
- `inventoryLogs`
- `reviews`

## Seed Data

You have two ways to populate products for development.

### Option 1. Use the seed script

```bash
node scripts/seed.mjs
```

This inserts sample sporting goods products into Firestore.

### Option 2. Add products through the admin panel

If you prefer to enter products manually, the admin UI supports creating and editing products directly in the browser.

Additional notes and sample product data are documented in `SEED_DATA.md`.

## Admin Setup

New users are created with the `customer` role by default.

To create an admin account:

1. Register a user through the app.
2. Open the Firebase Console.
3. Go to Firestore and locate that user's document in the `users` collection.
4. Change the `role` field from `customer` to `admin`.
5. Sign in again and open `/admin`.

## Usage Information

### Customer flow

1. Open the home page and browse featured products or jump into the full catalogue.
2. Filter into a sport or open a product detail page.
3. Add items to the cart.
4. Register or sign in before checkout.
5. Complete the shipping form and place the order.
6. Review previous orders from the orders page.

### Admin flow

1. Sign in with an account that has the `admin` role.
2. Open `/admin`.
3. Use the dashboard to review product count, order count, revenue, and low-stock items.
4. Create, edit, or delete products.
5. Review order data and inventory-related entries.

## Scripts

- `npm run dev` - start the Vite development server
- `npm run build` - type-check and create a production build
- `npm run preview` - preview the production build locally
- `npm run lint` - run ESLint

## Notes

- Cart data is stored in local storage under the `apex-cart` key.
- Checkout creates an order in Firestore and reduces stock for each purchased item.
- If Firestore is empty, the homepage can load without featured products until data is added.

## Development Status

This repository is structured as a working university project rather than a fully productized storefront. The current setup is enough to demo the main ecommerce flow locally, especially once Firebase services and sample data are in place.
