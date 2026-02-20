# 🍽️ Canteen Order System

![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python)
![PySimpleGUI](https://img.shields.io/badge/GUI-PySimpleGUI-green)
![MongoDB](https://img.shields.io/badge/Database-MongoDB-brightgreen?logo=mongodb)
![License](https://img.shields.io/badge/License-MIT-yellow)

A complete **Canteen Order Management System** built with **Python** and **PySimpleGUI**, integrated with **MongoDB** for persistent data storage. This system streamlines the food ordering workflow with secure QR-based order verification and automated billing.

## 📌 Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Project Structure](#project-structure)
- [Technology Stack](#technology-stack)
- [Installation](#installation)
- [Configuration](#configuration)
- [Running the Applications](#running-the-applications)
- [Workflow](#workflow)
- [Module Descriptions](#module-descriptions)
- [License](#license)

## Overview

This project consists of three independent yet interconnected applications designed to manage the complete canteen ordering lifecycle:

- **Client App** – Customer-facing interface for browsing menu and placing orders
- **Admin App** – Management interface for controlling inventory and pricing
- **Scanner App** – QR verification tool for order validation and billing

The modular architecture ensures each component operates independently while sharing a unified database backend.

## 🚀 Features

### Client Module
- Browse available food items with real-time inventory
- View special/promotional items
- Place new orders with customization
- Access order history and status tracking
- Mark orders as takeaway
- Auto-generated secure QR codes for order verification
- Digital receipt management

### Admin Module
- Add/remove menu items
- Update pricing dynamically
- Manage inventory quantities
- Mark items as special promotions
- View all customer orders and statistics
- Order status management

### Scanner Module
- Scan and validate customer QR codes
- Detect and prevent fraudulent orders
- Generate itemized bills in real-time
- Mark orders as completed
- Transaction logging and verification

## 📂 Project Structure

```
canteen_order_system/
├── admin/
│   ├── main.py              # Admin application entry point
│   └── database/
│       ├── __init__.py
│       └── func.py          # Admin database operations
├── client/
│   ├── main.py              # Client application entry point
│   └── database/
│       ├── __init__.py
│       └── func.py          # Client database operations
├── scanner/
│   ├── main.py              # Scanner application entry point
│   └── database/
│       ├── __init__.py
│       └── func.py          # Scanner database operations
├── __init__.py
├── config.py                # Configuration settings
├── requirements.txt         # Python dependencies
└── README.md               # This file
```

## 🛠 Technology Stack

| Component | Technology |
|-----------|-----------|
| Language | Python 3 |
| GUI Framework | PySimpleGUI |
| Database | MongoDB |
| QR Processing | qrcode, pyzbar |
| Image Processing | Pillow, OpenCV, numpy |
| Data Persistence | TinyDB (local storage) |

## ⚙️ Installation

### Prerequisites
- Python 3.7 or higher
- MongoDB server (local or cloud instance)
- pip package manager

### Step 1: Clone the Repository

```bash
git clone https://github.com/your-username/canteen-order-system.git
cd canteen-order-system
```

### Step 2: Create a Virtual Environment (Optional but Recommended)

```bash
python -m venv venv
# On Windows
venv\Scripts\activate
# On macOS/Linux
source venv/bin/activate
```

### Step 3: Install Dependencies

```bash
pip install -r requirements.txt
```

### Step 4: Configure MongoDB

Edit `config.py` and add your MongoDB connection URL:

```python
MONGO_URL = "mongodb+srv://username:password@cluster.mongodb.net/canteen"
# Or for local MongoDB:
MONGO_URL = "mongodb://localhost:27017/canteen"
```

## 🔧 Configuration

Update the `config.py` file with your settings:

```python
# MongoDB Connection URL
MONGO_URL = "YOUR MONGODB URL HERE"

# Optional: Add other configuration settings as needed
DATABASE_NAME = "canteen_order_system"
```

## Running the Applications

### Run Client Application
```bash
python client/main.py
```
Allows customers to browse menu and place orders.

### Run Admin Application
```bash
python admin/main.py
```
Enables canteen managers to manage inventory and pricing.

### Run Scanner Application
```bash
python scanner/main.py
```
QR code scanner for order verification and billing.

## 📊 Workflow

```
Customer Places Order (Client App)
          ↓
Order stored in MongoDB
          ↓
QR Code generated and displayed
          ↓
Customer shows QR to staff (Scanner App)
          ↓
Scanner validates and generates bill
          ↓
Order marked as completed
```

## 🔐 Module Descriptions

### Client Module (`client/`)
- Provides a user-friendly interface for customers
- Fetches available items from the database
- Processes order placement and generates QR codes
- Stores order history locally and in MongoDB

### Admin Module (`admin/`)
- Supplies backend management capabilities
- Manages menu items, pricing, and inventory
- Processes special promotions
- Views analytics and order statistics

### Scanner Module (`scanner/`)
- Scans and decodes QR codes from orders
- Validates authenticity against stored tokens
- Retrieves order details from MongoDB
- Generates itemized bills and confirms completion

## 📝 License

This project is licensed under the MIT License. See the LICENSE file for details.

---

**For questions or contributions, please open an issue or contact the development team.**
