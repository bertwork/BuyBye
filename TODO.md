# BuyBye - TODO 📝

## 🔐 Authentication
- [ ] Login
- [ ] Register with role selection (Buyer / Seller)
- [ ] Password hashing (djb2)

---

## 🏪 Seller — Store Management
- [ ] `createStore()` — create a new store, save to stores.csv
- [ ] `viewMyStores()` — display all stores by seller_id
- [ ] `switchActiveStore()` — select which store to manage
- [ ] `updateStore()` — update store name or description
- [ ] `deleteStore()` — remove store from stores.csv

---

## 🏪 Seller — Product Management (per active store)
- [ ] `addProduct()` — save new product to products.csv linked to store_id
- [ ] `viewMyProducts()` — display all products by store_id
- [ ] `updateProduct()` — update product fields by product_id
- [ ] `deleteProduct()` — remove product from products.csv
- [ ] `searchProduct()` — search by name or category

---

## 🏪 Seller — Sales Tracking
- [ ] `viewSellerOrders()` — view all orders for seller's products
- [ ] Display total sales per store

---

## 🛒 Buyer Features
- [ ] `browseStores()` — display all stores
- [ ] `browseStoreProducts()` — browse products in a selected store
- [ ] `browseAllProducts()` — browse all products globally
- [ ] `searchProductGlobal()` — search products across all stores
- [ ] `searchProductInStore()` — search products within a specific store
- [ ] `buyProduct()` — place order, update stock, save to orders.csv
- [ ] `viewMyOrders()` — display buyer's order history

---

## ⚙️ Core / Utilities
- [ ] `validateInput()` — input validation with try/catch
- [ ] `trim()` — trim whitespace from input
- [ ] `toLower()` — convert string to lowercase
- [ ] `pauseScreen()` — pause until Enter is pressed
- [ ] Splash screen
- [ ] Main menu
- [ ] Seller menu skeleton
- [ ] Buyer menu skeleton
- [ ] CSV structure planned
- [ ] Folder structure set up
- [ ] Update menus to reflect store system
- [ ] Add stores.h / stores.cpp

---

## 💡 Future Ideas (v2.0+)
- [ ] Location-based store browsing (filter by city/area)
- [ ] Product ratings and reviews
- [ ] Discount / promo system
- [ ] Admin role
- [ ] Low stock alerts for sellers
- [ ] Delivery tracking