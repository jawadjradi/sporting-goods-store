# Sporting Goods Store - Seed Data Script
# Run this from the Firebase Console or via a script after setting up Firestore

This script is for manually seeding your Firestore database with sample data.

## Quick Seed via Browser Console

After logging into your app as an admin, open browser console and run:

```js
// Import is already loaded via the app
const { collection, addDoc, serverTimestamp } = await import('https://www.gstatic.com/firebasejs/11.6.0/firebase-firestore.js');

// You can add products via the Admin Panel UI instead
```

## Sample Products to Add via Admin Panel

| Name | Brand | Price | Sport | Category | Stock |
|------|-------|-------|-------|----------|-------|
| Air Zoom Pegasus 41 | Nike | 129.99 | running | shoes | 50 |
| Ultraboost 24 | Adidas | 189.99 | running | shoes | 35 |
| Curry 11 | Under Armour | 159.99 | basketball | shoes | 25 |
| KD 17 | Nike | 149.99 | basketball | shoes | 30 |
| Predator Edge | Adidas | 119.99 | football | shoes | 40 |
| Phantom GX | Nike | 134.99 | football | shoes | 20 |
| Pro Staff RF97 | Wilson | 249.99 | tennis | equipment | 15 |
| Pure Aero | Babolat | 229.99 | tennis | equipment | 18 |
| Speedo Fastskin | Speedo | 89.99 | swimming | apparel | 60 |
| Training Gloves Pro | Nike | 34.99 | training | accessories | 100 |
| Dri-FIT Running Tee | Nike | 44.99 | running | apparel | 80 |
| Compression Shorts | Under Armour | 39.99 | training | apparel | 70 |

## Setting Up Admin User

1. Register a new account in the app
2. Go to Firebase Console > Firestore
3. Find the user document in the `users` collection
4. Change `role` from `"customer"` to `"admin"`
