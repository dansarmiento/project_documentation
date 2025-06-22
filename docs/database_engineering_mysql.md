# Database Engineering Project: Little Lemon Restaurant

## Overview

This project, `database_engineering_mysql`, focuses on the design and implementation of a relational database for the Little Lemon Restaurant.  It utilizes MySQL and includes various SQL scripts for database schema creation, data manipulation, stored procedures, and view creation. The project demonstrates practical database engineering skills, including forward engineering, data modeling, and the use of advanced SQL features.


## Key Features

* **Database Schema Design:** A complete relational database schema for managing restaurant data (likely bookings, orders, etc.).
* **SQL Scripts:**  Multiple SQL files implementing database creation, stored procedures, views, and other SQL operations.
* **Data Modeling Diagram:** A visual representation of the database schema (`little_lemon_sales_data_model.png`).
* **Stored Procedures:**  A suite of stored procedures for managing restaurant bookings (add, update, cancel, check).
* **Views and Queries:** SQL queries demonstrating data retrieval using joins and subqueries.
* **Prepared Statements:** Example of using prepared statements for efficient and secure query execution.


## Project Structure

The project directory contains the following key files and folders:

* **`LittleLemonDB_forward_engineer.sql`:**  SQL script for creating the initial database schema.
* **`db_capstone_project.ipynb`:**  Likely a Jupyter Notebook containing analysis or experimentation related to the database.
* **`little_lemon_sales_data_model.png`:**  Diagram visualizing the database schema.
* **`little_lemon_sales_model.mwb`:**  Likely a database model file (MySQL Workbench).
* **`m2_*.sql`:**  Series of SQL files demonstrating specific database operations (stored procedures, views, queries, etc.).  These files are likely modular components for different aspects of the database management.
* **`README.md`:** This file.


## Getting Started

This project requires a MySQL server to be installed and running.  The following steps outline how to use the provided SQL scripts:

1. **Install MySQL:** Ensure you have MySQL Server installed and configured on your system.
2. **Create a MySQL database:** Create a new database (e.g., `LittleLemonDB`).
3. **Execute the schema script:** Connect to the newly created database and execute `LittleLemonDB_forward_engineer.sql` to create the tables.  This can be done using the MySQL command-line client or a GUI tool like MySQL Workbench.
4. **Execute other SQL scripts:**  Sequentially execute the other `.sql` files (e.g., those starting with `m2_`) to create stored procedures, views, and populate the database with sample data (if any is provided).  The order might be important; consult the file names for logical execution order.
5. **Interact with the database:** Use the MySQL client or a preferred tool to query the database using the created views and stored procedures.

**Example (using the MySQL command-line client):**

```bash
mysql -u your_username -p LittleLemonDB < LittleLemonDB_forward_engineer.sql
mysql -u your_username -p LittleLemonDB < m2_create_stored_procedure.sql
# ... execute other .sql files ...
```

Remember to replace `your_username` with your MySQL username.  The Jupyter Notebook (`db_capstone_project.ipynb`) may provide further instructions or examples.  Consult the file `little_lemon_sales_data_model.png` for understanding the database schema.
