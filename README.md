# mini-project-main

# 🛒 ShopZone — E-Commerce Mini Website

> A complete dynamic E-Commerce mini website built with **Core PHP**, **MySQL**, **HTML**, **CSS**, and **JavaScript** as an academic project.

---

## 👥 Group Members

| # | Name |
|---|------|
| 1 | gohilmitrajsinh |


**Tech Stack:** PHP (Core PHP) · MySQL · HTML · CSS · JavaScript  
**Semester:** 4th Semester | BCA / B.Sc. IT  

---

## 📋 Project Overview

ShopZone is a fully functional e-commerce mini website that demonstrates fundamental web development concepts including:
- Dynamic product management (CRUD)
- Session-based shopping cart
- Admin authentication & dashboard
- Form handling with validation
- MySQL database integration

---

## ✨ Features

### 🛍️ User Features
- **Product Listing** — Browse all products dynamically loaded from the database
- **Add to Cart** — Session-based cart (no login required for users)
- **Cart Management** — View cart, update quantities, remove items
- **Checkout** — Fill delivery details and simulate order placement
- **Order Confirmation** — Order success page with order summary

### ⚙️ Admin Features
- **Secure Login** — Session-based authentication (admin only)
- **Dashboard** — Overview with stats (products, orders, revenue)
- **Product CRUD** — Add, Edit, Delete, View all products
- **Image Upload** — Upload product images with validation
- **Order Management** — View all customer orders with details
- **Logout** — Secure session destruction

---

## 🗄️ Database Structure

### Table: `users`
| Column | Type | Description |
|--------|------|-------------|
| id | INT (PK, AI) | Unique user ID |
| username | VARCHAR(50) | Login username |
| password | VARCHAR(255) | MD5 hashed password |
| role | ENUM | `admin` or `user` |
| created_at | TIMESTAMP | Account creation time |

### Table: `products`
| Column | Type | Description |
|--------|------|-------------|
| id | INT (PK, AI) | Unique product ID |
| name | VARCHAR(100) | Product name |
| price | DECIMAL(10,2) | Product price |
| description | TEXT | Product description |
| image | VARCHAR(255) | Image filename |
| created_at | TIMESTAMP | Date added |

### Table: `orders`
| Column | Type | Description |
|--------|------|-------------|
| id | INT (PK, AI) | Order ID |
| customer_name | VARCHAR(100) | Customer's full name |
| customer_email | VARCHAR(100) | Customer's email |
| customer_address | TEXT | Delivery address |
| total_amount | DECIMAL(10,2) | Total including tax |
| order_date | TIMESTAMP | Order placement time |

### Table: `order_items`
| Column | Type | Description |
|--------|------|-------------|
| id | INT (PK, AI) | Item ID |
| order_id | INT (FK) | Reference to orders.id |
| product_id | INT | Product reference |
| product_name | VARCHAR(100) | Product name (snapshot) |
| price | DECIMAL(10,2) | Price at time of order |
| quantity | INT | Quantity ordered |

---

## 📁 Folder Structure

```
ecommerce/
├── index.php               ← Homepage / Product listing
├── config/
│   └── db.php              ← Database connection
├── database/
│   └── ecommerce.sql       ← SQL schema + seed data
├── assets/
│   ├── css/
│   │   └── style.css       ← Main stylesheet
│   └── images/             ← Product images (uploaded here)
├── admin/
│   ├── login.php           ← Admin login
│   ├── logout.php          ← Admin logout
│   ├── auth_check.php      ← Session guard
│   ├── dashboard.php       ← Admin dashboard
│   ├── products.php        ← List + delete products
│   ├── add_product.php     ← Add new product
│   ├── edit_product.php    ← Edit existing product
│   └── orders.php          ← View all orders
└── user/
    ├── add_to_cart.php     ← Cart handler
    ├── cart.php            ← Cart page
    ├── checkout.php        ← Checkout form
    └── order_success.php   ← Order confirmation
```

---

## 🚀 How to Run Locally (XAMPP)

### Prerequisites
- [XAMPP](https://www.apachefriends.org/) installed (includes Apache + MySQL + PHP)

### Step-by-Step Setup

**Step 1: Start XAMPP**
```
Open XAMPP Control Panel
Start → Apache
Start → MySQL
```

**Step 2: Place Project Files**
```
Copy the entire `ecommerce` folder into:
C:\xampp\htdocs\ecommerce\
```

**Step 3: Create Database**
```
1. Open browser → http://localhost/phpmyadmin
2. Click "New" to create a new database  
   (or just import the SQL file — it auto-creates the DB)
3. Click "Import" tab
4. Choose file: ecommerce/database/ecommerce.sql
5. Click "Go"
```

**Step 4: Configure Database (if needed)**
```
Open: ecommerce/config/db.php
Change DB_USER and DB_PASS if you have custom credentials.
Default XAMPP: user=root, pass=(empty)
```

**Step 5: Run the Project**
```
Open browser → http://localhost/ecommerce/
```

---

## 🔐 Default Admin Login

| Field | Value |
|-------|-------|
| URL | http://localhost/ecommerce/admin/login.php |
| Username | `admin` |
| Password | `admin123` |

> ⚠️ **Security Note:** This project uses MD5 hashing for academic purposes only. In production, use `password_hash()` and `password_verify()` instead.

---

## 🖥️ Pages Reference

| Page | URL | Description |
|------|-----|-------------|
| Homepage | `/index.php` | Product grid listing |
| Cart | `/user/cart.php` | Shopping cart |
| Checkout | `/user/checkout.php` | Order placement |
| Admin Login | `/admin/login.php` | Admin authentication |
| Dashboard | `/admin/dashboard.php` | Admin overview |
| Add Product | `/admin/add_product.php` | Create new product |
| Products | `/admin/products.php` | Manage all products |
| Orders | `/admin/orders.php` | View all orders |

---

## 📝 Notes

- Cart is **session-based** — no user registration needed to shop
- Images are uploaded to `assets/images/` — ensure folder is **writable** (chmod 755)
- GST of 18% is automatically calculated at checkout
- All inputs are sanitized with `mysqli_real_escape_string()` and `htmlspecialchars()`

---

## 📄 License

This project is created for academic purposes. Free to use and modify.

---

