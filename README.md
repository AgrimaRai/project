# Giftos - Online Gift Shop

A modern web application for an online gift shop built with Node.js, Express, and MySQL.


## Installation

1. Clone the repository:
```bash
git clone https://github.com/AgrimaRai/project.git
cd project
```

2. Install dependencies:
```bash
npm install express mysql2 bcrypt body-parser
```

3. Set up MySQL database:
```bash
mysql -u root -p
CREATE DATABASE giftos_db;
CREATE USER 'giftos_user'@'localhost' IDENTIFIED BY 'giftos_password';
GRANT ALL PRIVILEGES ON giftos_db.* TO 'giftos_user'@'localhost';
FLUSH PRIVILEGES;
```

The application automatically creates the following tables:

### Users Table
```sql
CREATE TABLE users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    username VARCHAR(255) NOT NULL,
    email VARCHAR(255) NOT NULL UNIQUE,
    password VARCHAR(255) NOT NULL
)
```

### Products Table
```sql
CREATE TABLE products (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(255) NOT NULL,
    price DECIMAL(10,2) NOT NULL,
    image_data LONGBLOB NOT NULL,
    image_name VARCHAR(255) NOT NULL
)
```

### Testimonials Table
```sql
CREATE TABLE testimonials (
    id INT AUTO_INCREMENT PRIMARY KEY,
    author VARCHAR(255) NOT NULL,
    content TEXT NOT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
)
```


## Running the Application

Start the server:
```bash
node server.js
```

The application will be available at `http://localhost:3000`
