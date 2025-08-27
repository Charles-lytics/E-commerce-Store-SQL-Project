# E-commerce Store Database Schema

This repository contains the SQL schema for an **E-commerce Store** database.  
The schema is designed in MySQL and supports customer management, product catalog, payments, and order processing.

---

## 📂 Schema: `ecommerce_store`

### 1. CUSTOMER
Stores customer details.

- `CUSTOMER_ID` (PK, INT, AUTO_INCREMENT)  
- `FIRST_NAME`, `LAST_NAME` (VARCHAR)  
- `ADDRESS`, `CITY`, `STATE`, `COUNTRY`, `ZIPCODE` (VARCHAR)  
- `PHONE_NUMBER` (VARCHAR, UNIQUE)  
- `CUSTOMER_EMAIL` (VARCHAR, UNIQUE)

---

### 2. PRODUCT
Stores product catalog.

- `PRODUCT_ID` (PK, INT, AUTO_INCREMENT)  
- `PRODUCT_NAME` (VARCHAR)  
- `PRODUCT_TYPE` (VARCHAR)  
- `PRICE` (DECIMAL)  
- `QUANTITY` (INT)

---

### 3. PAYMENTS
Stores payment details.

- `PAYMENT_ID` (PK, INT, AUTO_INCREMENT)  
- `CUSTOMER_ID` (FK → CUSTOMER.CUSTOMER_ID)  
- `PAYMENT_TYPE` (VARCHAR)  
- `CREDIT_CARD_NUMBER` (CHAR)  
- `EXPIRY_DATE` (DATE)  
- `CVV` (CHAR)  
- `EMAIL_ID` (VARCHAR, optional)

---

### 4. ORDERS
Stores customer orders.

- `ORDER_ID` (PK, INT, AUTO_INCREMENT)  
- `DEVICE` (VARCHAR)  
- `PRODUCT_ID` (FK → PRODUCT.PRODUCT_ID)  
- `CUSTOMER_ID` (FK → CUSTOMER.CUSTOMER_ID)  
- `PAYMENT_ID` (FK → PAYMENTS.PAYMENT_ID)  
- `SHIPPING_ADDRESS`, `SHIPPING_CITY`, `SHIPPING_STATE`, `SHIPPING_COUNTRY` (VARCHAR)  
- `DELIVERED` (ENUM: 'YES'/'NO', default 'NO')

---

## 🔗 Relationships
- Each **Customer** can have multiple **Payments**.  
- Each **Customer** can place multiple **Orders**.  
- Each **Order** is linked to a **Product** and a **Payment method**.  
- Payments and Orders are tied back to **Customers**.

---

## 🚀 Usage
1. Clone this repository.  
2. Import the `ecommerce_store.sql` file into MySQL Workbench or any MySQL database.  
3. Start inserting customer, product, payment, and order records.

---

## 📜 License
This project is open-source and available under the MIT License.
