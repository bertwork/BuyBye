# BuyBye - App Flow 🗺️

## App Entry
```
Launch BuyBye
    ↓
==================== BuyBye ====================
    Where you buy things & your money says bye!
================================================
    ↓
[1] Login
[2] Register
[3] Exit
```

---

## Register Flow
```
[2] Register
    ↓
Enter username
    ↓
Enter password → Confirm password
    ↓
Select Role:
  [1] Buyer
  [2] Seller
    ↓
✅ Registration successful! → back to Main Menu
```

---

## Login Flow
```
[1] Login
    ↓
Enter username + password
    ↓
  ┌─ ❌ Invalid → retry
  └─ ✅ Success
        ↓
        ├── role = seller → Seller Menu
        └── role = buyer  → Buyer Menu
```

---

## 🏪 Seller Flow
```
Seller Menu
    ↓
[1] Manage My Stores
      ↓
      [1] Create Store
            → Enter store name + description
            → save to stores.csv
            → ✅ Store created!

      [2] View My Stores
            → display all stores by seller_id

      [3] Switch Active Store
            → select which store to manage
            → all product actions apply to this store

      [4] Update Store
            → update store name or description

      [5] Delete Store
            → confirm delete
            → remove from stores.csv

      [6] Back

[2] Manage Products  (based on active store)
      ↓
      [1] Add Product
            → Enter name, category, price, stock
            → save to products.csv linked to store_id

      [2] View My Products
            → display all products in active store

      [3] Update Product
            → select product → update fields

      [4] Delete Product
            → confirm delete
            → remove from products.csv

      [5] Search Product
            → search by name or category in active store

      [6] Back

[3] View Sales / Orders
      → display all orders for seller's products
      → show total sales per store

[4] Logout
```

---

## 🛒 Buyer Flow
```
Buyer Menu
    ↓
[1] Browse Stores
      → display all stores
      → select a store
      → browse products in that store
      → select product → Buy

[2] Browse All Products (global)
      → display all products across all stores
      → select product → Buy

[3] Search Product
      ↓
      [1] Search Globally
            → search by name or category across all stores
      [2] Search in a Specific Store
            → select store first
            → then search by name or category

[4] Buy Product
      → Enter product id
      → Enter quantity
      → confirm order
      → update stock in products.csv
      → save to orders.csv
      → ✅ Order placed!

[5] View My Orders
      → display all orders by buyer_id
      → show product name, store, quantity, total price, date

[6] Logout
```

---

## Logout Flow
```
[Logout]
    ↓
"Logging out... Goodbye, {username}! 👋"
    ↓
Back to Main Menu
```