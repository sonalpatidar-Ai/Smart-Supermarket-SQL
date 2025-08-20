# Smart-Supermarket-SQL
SQL Supermarket Management Database | Manage products, customers, sales &amp; employees with triggers &amp; reports . 

⚙️ Features

👥 Customer Management – Stores customer details (Name, Contact, Address).

📦 Product Management – Handles product categories, prices, and stock levels.

🧑‍💼 Employee Management – Maintains records of employees (Cashiers, Managers, Sales Assistants).

💳 Sales Transactions – Records daily sales and line items with product details.

🔒 Data Integrity – Trigger prevents negative stock after sales.

📊 Reports & Queries – Generate insights like:

  . Top customers by spending

  . Most sold products

  . Daily/Monthly revenue

  . Employee performance


🛠️ Tech Stack

1. Database: MySQL

2. Language: SQL (DDL, DML, Triggers)

3. Concepts Used:

4. Primary & Foreign Keys

5. Constraints & Triggers

6. Transactions

7. Data Normalization


📂 Project Structure

📦 SupermarketDB

 │── 📜 supermarket.sql       # Main SQL script (tables, inserts, triggers, sample data)
 
 │── 📜 README.md             # Project documentation
 
 │── 📜 queries.sql           # Example SQL queries for reports


 🚀 How to Run

1. Open MySQL Workbench / Command Line.

2. Run the script:

     SOURCE supermarket.sql;

3. Verify the database:

    SHOW DATABASES;
   
    USE SupermarketDB;
   
    SHOW TABLES;

4. Run sample queries from queries.sql.


📊 Sample Queries

-- Top 5 customers by total spending
SELECT c.Name, SUM(s.TotalAmount) AS TotalSpent
FROM Customers c
JOIN Sales s ON c.CustomerID = s.CustomerID
GROUP BY c.CustomerID
ORDER BY TotalSpent DESC
LIMIT 5;

-- Most sold products
SELECT p.ProductName, SUM(sd.Quantity) AS TotalSold
FROM SaleDetails sd
JOIN Products p ON sd.ProductID = p.ProductID
GROUP BY sd.ProductID
ORDER BY TotalSold DESC
LIMIT 5;

-- Daily revenue
SELECT SaleDate, SUM(TotalAmount) AS Revenue
FROM Sales
GROUP BY SaleDate;


📈 Future Enhancements

1. Add billing system (auto bill generation).

2. Create stored procedures for common tasks.

3. Build a frontend app to interact with this database.


👨‍💻 Author

Sonal Patidar 
