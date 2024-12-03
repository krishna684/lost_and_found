# 📦 Lost & Found Management System

**A comprehensive PHP-based application leveraging a robust RDBMS for managing lost and found items.**

---

## 📖 Project Overview

This application demonstrates the use of a relational database (RDBMS) to manage, organize, and retrieve data for lost and found items. Users can:

- Report lost items 🕵️‍♂️
- Report found items 🛠️
- View all listed items 📜
- Claim found items 🎯

The backend uses MySQL for structured data storage, adhering to **Third Normal Form (3NF)** to ensure minimal redundancy and optimal performance.

---

## ✨ Features

- **Data Integrity**: Ensures consistency and reduces redundancy through a normalized schema.
- **Ease of Use**: User-friendly interface for all key operations.
- **Dynamic Queries**: SQL queries dynamically adapt based on user inputs.
- **Scalable Design**: Flexible schema for handling large-scale data.

---

## 🛠️ Tech Stack

- **Frontend**: HTML, CSS, JavaScript
- **Backend**: PHP
- **Database**: MySQL
- **Server**: Apache/Nginx

---

## 📂 Directory Structure

```plaintext
├── claim_item.php           # Handles item claim processes
├── claim_process.php        # Processes item claim requests
├── index.php                # Main landing page
├── navbar.php               # Shared navigation bar
├── report_found.php         # Form for reporting found items
├── report_lost.php          # Form for reporting lost items
├── view_items.php           # Displays all reported items
├── database/
│   ├── schema.sql           # SQL script for creating the database schema
│   ├── seed_data.sql        # SQL script for populating tables with sample data
├── assets/
│   ├── css/                 # CSS files for styling
│   ├── js/                  # JavaScript files for interactivity
└── README.md                # Project documentation
```

---

## 🏗️ Database Schema

The database adheres to **3NF**, ensuring:

- Each table has a primary key.
- Non-key columns depend solely on the primary key.
- No transitive dependencies exist.

### **Tables**

1. **Users**: Stores user details.
2. **Items**: Records details of lost/found items.
3. **Claims**: Tracks claim requests.

### **ER Diagram**

> (You can use tools like Lucidchart, dbdiagram.io, or MySQL Workbench to create and include an ER diagram image.)

---

## 🚀 Getting Started

### 1. Prerequisites

- **PHP**: Version 7.4 or later
- **MySQL**: Version 8.0 or later
- **Web Server**: Apache or Nginx

### 2. Setup Instructions

#### Clone the Repository

```bash
git clone https://github.com/<your-username>/lost-found-management.git
cd lost-found-management
```

#### Configure the Database

1. Import the database schema:
   ```bash
   mysql -u <username> -p < database_name> < database/schema.sql
   ```

2. Populate the database with sample data:
   ```bash
   mysql -u <username> -p < database_name> < database/seed_data.sql
   ```

3. Update the `config.php` file with your database credentials:
   ```php
   <?php
   $dbHost = 'localhost';
   $dbUser = 'your_username';
   $dbPass = 'your_password';
   $dbName = 'your_database_name';
   ?>
   ```

#### Run the Application

1. Move the project files to your server's root directory:
   ```bash
   cp -r * /var/www/html/
   ```
2. Open a browser and navigate to:
   ```
   http://localhost/index.php
   ```

---

## 🔍 SQL Queries Example

Here’s an example of an optimized query used in the application:

```sql
SELECT i.item_id, i.item_name, u.user_name, c.claim_date
FROM items AS i
LEFT JOIN claims AS c ON i.item_id = c.item_id
LEFT JOIN users AS u ON c.user_id = u.user_id
WHERE i.status = 'found';
```

---

## 🧑‍💻 Contributing

Contributions are welcome! Feel free to open an issue or submit a pull request. Please adhere to the [Code of Conduct](CODE_OF_CONDUCT.md).

---

## 📜 License

This project is licensed under the MIT License. See the [LICENSE](LICENSE.md) file for details.

---

## 🌟 Acknowledgments

- **PHP Docs**: [php.net](https://www.php.net/)
- **MySQL Reference**: [dev.mysql.com](https://dev.mysql.com/doc/)