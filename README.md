# project-7
Billing Software
This project is a Billing Software System built using Python (Tkinter for GUI) and MySQL for backend database storage. It allows users to enter customer details (name and phone number), input product information (name, rate, quantity), and dynamically generate a printable bill showing all purchased items with their quantities and prices. The software calculates the total payable amount and displays it in a bill format. All transaction data can be saved into a MySQL database for future reference and record-keeping. The interface is user-friendly and ideal for small retail shops or businesses looking to automate their billing process. Key features include adding items to the bill, clearing inputs, exiting the application, and generating a formatted bill display area that summarizes the purchase. This project demonstrates GUI development with Tkinter, real-time calculations, and database integration in a practical, business-oriented Python application.

# 🧾 Billing Software Using Python (Tkinter) and MySQL

This is a simple yet fully functional **Billing Software System** created using **Python's Tkinter library** for the graphical user interface and **MySQL** as the backend for data storage. The software enables easy product billing, real-time total calculation, and customer data handling — ideal for small businesses, retail shops, and local stores.

## ✅ Features

- GUI-based billing system using Tkinter
- Add multiple items with product name, rate, and quantity
- Automatically calculate the total payable amount
- Generates a formatted printable bill
- Stores customer and billing data in **MySQL**
- Buttons for: Add Item, Generate Bill, Clear, Exit
- Unique Bill Number generation
- Displays customer details on the bill
- Real-time item display with quantity and price

## 🛠 Technologies Used

- **Python** (GUI: Tkinter)
- **MySQL** (Data storage)
- **SQL Connector** (`mysql-connector-python`)

## 🗃️ Database Schema (MySQL)

```sql
CREATE DATABASE billing_system;

USE billing_system;

CREATE TABLE bills (
    bill_no INT PRIMARY KEY,
    customer_name VARCHAR(100),
    phone VARCHAR(15),
    total_amount INT,
    created_at DATETIME DEFAULT CURRENT_TIMESTAMP
);

CREATE TABLE bill_items (
    id INT AUTO_INCREMENT PRIMARY KEY,
    bill_no INT,
    product_name VARCHAR(100),
    rate INT,
    quantity INT,
    FOREIGN KEY (bill_no) REFERENCES bills(bill_no)
);
