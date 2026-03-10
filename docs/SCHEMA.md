# BuyBye - CSV Schema 🗄️

## Overview
BuyBye uses CSV files as its database. Each file represents a table, and relationships between tables are handled manually using IDs (foreign keys).

---

## 📄 users.csv
Stores all registered user accounts.

| Field    | Type   | Description                  |
|----------|--------|------------------------------|
| id       | int    | unique user ID (auto increment) |
| username | string | unique username              |
| password | int    | hashed password (djb2)       |
| role     | string | "buyer" or "seller"          |

**Example:**
```
1,john,48291039,seller
2,jane,93820194,buyer
3,bob,19284756,buyer
```

---

## 📄 stores.csv
Stores all seller stores / branches.

| Field       | Type   | Description                        |
|-------------|--------|------------------------------------|
| id          | int    | unique store ID (auto increment)   |
| seller_id   | int    | FK → users.csv (must be a seller)  |
| store_name  | string | name of the store                  |
| description | string | short description of the store     |

**Example:**
```
1,1,John's Gadgets,Best gadgets in town!
2,1,John's Clothing,Trendy clothes for less
3,2,Jane's Bakery,Fresh baked goods daily
```

---

## 📄 products.csv
Stores all product listings per store.

| Field    | Type   | Description                       |
|----------|--------|-----------------------------------|
| id       | int    | unique product ID (auto increment)|
| store_id | int    | FK → stores.csv                   |
| name     | string | product name                      |
| category | string | product category                  |
| price    | double | product price                     |
| stock    | int    | available stock quantity          |

**Example:**
```
1,1,Wireless Mouse,Electronics,599.00,50
2,1,Mechanical Keyboard,Electronics,1299.00,30
3,2,Plain T-Shirt,Clothing,199.00,100
```

---

## 📄 orders.csv
Stores all buyer orders.

| Field       | Type   | Description                        |
|-------------|--------|------------------------------------|
| id          | int    | unique order ID (auto increment)   |
| buyer_id    | int    | FK → users.csv (must be a buyer)   |
| product_id  | int    | FK → products.csv                  |
| store_id    | int    | FK → stores.csv                    |
| quantity    | int    | quantity ordered                   |
| total_price | double | quantity × product price           |
| date        | string | date of order (YYYY-MM-DD)         |

**Example:**
```
1,2,1,1,2,1198.00,2025-01-10
2,3,3,2,5,995.00,2025-01-11
```

---

## 🔗 Relationships
```
users ──< stores       (one seller → many stores)
stores ──< products    (one store → many products)
users ──< orders       (one buyer → many orders)
products ──< orders    (one product → many orders)
stores ──< orders      (one store → many orders)
```

---

## ⚠️ Notes
- CSV files are stored in the `data/` folder
- There is no auto referential integrity — deletions must be handled manually in code
- Deleting a store should also delete its products
- Deleting a product should also handle related orders
- All IDs are auto incremented by reading the last ID in the file