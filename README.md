# **FinTrack: Bank Management System** 🏦

A secure and user-friendly bank management system built using **Flask**, **MySQL**, and **Python**. It allows users to register, log in, and manage their bank accounts with transaction tracking.

---

## 🚀 **Tech Stack**
- **Backend:** Flask, Python
- **Database:** MySQL
- **Frontend:** HTML, CSS
- **User Authentication:** Flask-Login

---

## 📌 **Features**
✅ **User Registration** – Secure signup with unique usernames.  
✅ **Login System** – Encrypted password authentication.  
✅ **Dashboard** – View account balance & transaction history.  
✅ **Transaction History** – Track deposits & withdrawals.  

---

## 🛠️ **Installation & Setup**
Follow these steps to set up the project locally.

### **Prerequisites**
- **Python** (>= 3.x)
- **MySQL Server**
- **pip** (Python package manager)

---

### **Step 1: Clone the Repository**
```bash
git clone https://github.com/your-username/fintrack.git
cd fintrack
```

---

### **Step 2: Create a Virtual Environment**
```bash
python -m venv venv
```

---

### **Step 3: Activate Virtual Environment**
#### **For Windows:**
```bash
venv\Scripts\activate
```
#### **For macOS/Linux:**
```bash
source venv/bin/activate
```

---

### **Step 4: Install Required Dependencies**
```bash
pip install -r requirements.txt
```

---

### **Step 5: MySQL Database Setup**
1. Start your MySQL server.
2. Log in to MySQL:
```bash
mysql -u root -p
```
3. Run the following SQL queries to create the database and tables:
```sql
CREATE DATABASE bank_db;
USE bank_db;

CREATE TABLE users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    username VARCHAR(50) NOT NULL UNIQUE,
    password VARCHAR(255) NOT NULL,
    balance DECIMAL(10,2) DEFAULT 0.00
);

CREATE TABLE transactions (
    id INT AUTO_INCREMENT PRIMARY KEY,
    user_id INT,
    type ENUM('Deposit', 'Withdraw'),
    amount DECIMAL(10,2),
    transaction_date TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    FOREIGN KEY (user_id) REFERENCES users(id)
);
```

---

### **Step 6: Update Database Configuration**
Edit the `config.py` file and update the MySQL connection details:
```python
DB_CONFIG = {
    'host': 'localhost',
    'user': 'root',
    'password': 'yourpassword',
    'database': 'bank_db'
}
```

---

### **Step 7: Run the Flask Application**
```bash
python app.py
```
The server should now start at:  
🔗 **http://127.0.0.1:5000**

---

## 🎯 **How to Check if the Project is Working?**
- Open **http://127.0.0.1:5000** in your browser.
- Click on **Register** and create a new user.
- Log in using the registered credentials.
- Try adding or withdrawing money to see transaction records.

---

## 🤝 **Contributing**
Want to improve this project? Follow these steps:  
1. **Fork** the repository  
2. **Create** a new branch  
3. **Make** your changes  
4. **Submit** a Pull Request  

---

## 📜 **License**
This project is licensed under the MIT License. See the **LICENSE** file for details.

---
  
🎉 **Happy Coding!**
