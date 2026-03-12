# BuyBye 👋💸
> *Where you buy things & your money says bye!*

A console-based mini marketplace built in C++ where users can register as a **Buyer** or **Seller** and trade products across multiple stores.

---

## 📦 Features

### 🔐 Authentication
- Register with a chosen role (Buyer or Seller)
- Login with username and password
- Password hashing for security

### 🏪 Seller
- Create and manage multiple stores (branches)
- Switch between active stores
- Add, view, update, and delete products per store
- Track sales and incoming orders

### 🛒 Buyer
- Browse all stores or a specific store
- Browse all products globally or within a specific store
- Search products globally or within a specific store
- Buy products
- View order history

### ⚙️ General
- Stock quantity tracking
- Product categories
- Input validation throughout
- CSV file-based database

---

## 📁 Project Structure
```
BuyBye/
  src/
    main.cpp           → entry point, menus
    auth/
      auth.cpp         → login, register, password hashing
      auth.h
    stores/
      stores.cpp       → store management (CRUD)
      stores.h
    products/
      products.cpp     → product CRUD and search
      products.h
    orders/
      orders.cpp       → buy product, order history, sales tracking
      orders.h
    utils/
      utils.cpp        → shared utility functions
      utils.h
  data/
    users.csv          → user accounts
    stores.csv         → seller stores / branches
    products.csv       → product listings
    orders.csv         → order history
  docs/
    FLOW.md            → app flow diagrams
    SCHEMA.md          → CSV structure details
  README.md
  TODO.md
  .gitignore
```

---

## 🗄️ CSV Structure
```
users.csv
  id, username, password(hashed), role

stores.csv
  id, seller_id(FK), store_name, description

products.csv
  id, store_id(FK), name, category, price, stock

orders.csv
  id, buyer_id(FK), product_id(FK), store_id(FK), quantity, total_price, date
```

---

## 🗺️ App Flow
```
Launch BuyBye
    ↓
[1] Login
[2] Register → choose role (Buyer / Seller)
[3] Exit
    ↓
    ├── 🏪 Seller Menu
    │     [1] Manage My Stores
    │           [1] Create Store
    │           [2] View My Stores
    │           [3] Switch Active Store
    │           [4] Back
    │     [2] Manage Products (active store)
    │           [1] Add Product
    │           [2] View Products
    │           [3] Update Product
    │           [4] Delete Product
    │           [5] Back
    │     [3] View Sales / Orders
    │     [4] Search Product
    │     [5] Logout
    │
    └── 🛒 Buyer Menu
          [1] Browse All Stores
                → Select a Store → Browse Products
          [2] Browse All Products (global)
          [3] Search Product
                [1] Search globally
                [2] Search in a specific store
          [4] Buy Product
          [5] View My Orders
          [6] Logout
```

---

## 🛠️ Built With
- **Language** — C++
- **File Handling** — fstream
- **Database** — CSV files

---

## 👨‍💻 Author
- BertWork

---

*Made with 💸 and a sense of humor*