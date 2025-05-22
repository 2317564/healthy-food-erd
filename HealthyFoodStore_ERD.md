# Healthy Food Store – Entity Relationship Diagram (ERD)

This ERD represents the data structure of a small business that sells healthy food products, including fruits, vegetables, 
grains, and supplements. It tracks what products are available, customer information, sales transactions, and stock levels.

---

## 🥦 Overview

The store needs to manage:
- A catalog of healthy food products
- Customer information
- Sales history
- Inventory for each product

---

## 📦 Entities

### **PRODUCT**
- Stores data about each food item.
- Example: “Organic Bananas”, “Almond Milk”, “Quinoa”.

### **CUSTOMER**
- Stores name and contact details of each customer.

### **SALE**
- Tracks purchases, including product, customer, date, and quantity.

### **INVENTORY**
- Tracks how much of each product is in stock and where it is stored.

---

## 🔗 Relationships

- Each **Customer** can place many **Sales**.
- Each **Sale** is linked to one **Product**.
- Each **Product** has one associated **Inventory** record.

---

## ✅ Business Value

- Helps the store manage product availability
- Tracks customer purchases for loyalty or marketing
- Supports restocking by showing real-time inventory levels

```mermaid
erDiagram
    PRODUCT {
        int product_id PK
        string name
        string category
        float price
    }

    CUSTOMER {
        int customer_id PK
        string name
        string email
        string phone
    }

    SALE {
        int sale_id PK
        date sale_date
        int customer_id FK
        int product_id FK
        int quantity
    }

    INVENTORY {
        int inventory_id PK
        int product_id FK
        int stock_quantity
        string location
    }

    PRODUCT ||--o{ SALE : "is sold in"
    CUSTOMER ||--o{ SALE : "places"
    PRODUCT ||--|| INVENTORY : "tracked by"
```
