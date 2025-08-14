# Elevate-Labs--Task7

Features:

Add Employee: Insert a new employee record with name, department, and salary.

View Employees: Display all employee records in a tabular format.


Update Employee: Modify an existing employee's details based on their ID.

Delete Employee: Remove an employee record by ID.

Exit: Close the application.

Setup Instructions:

1. Database Setup:
   
Install MySQL Server if not already installed.

Create a database named employee_db using the following SQL:

CREATE DATABASE employee_db;
USE employee_db;
CREATE TABLE employees (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    department VARCHAR(50) NOT NULL,
    salary DOUBLE NOT NULL
);

Update the database connection details in EmployeeDatabaseApp.java:

Replace your_password_here with your MySQL root password.

Ensure the URL matches your MySQL server configuration (e.g., jdbc:mysql://localhost:3306/employee_db?useSSL=false).

2. Running the Application:

Ensure MySQL Server is running.

Run the Java application:

javac EmployeeDatabaseApp.java
java EmployeeDatabaseApp

Follow the console menu to perform CRUD operations.

Code Explanation:

Database Connection: Uses DriverManager to establish a connection to the MySQL database with the specified URL, username, and password.

JDBC Driver: Loads the MySQL JDBC driver using Class.forName("com.mysql.cj.jdbc.Driver").

CRUD Operations:

Create: Uses PreparedStatement to insert employee data safely, preventing SQL injection.

Read: Executes a SELECT query with Statement and processes results with ResultSet.

Update: Updates employee records using PreparedStatement with parameterized queries.

Delete: Removes employee records by ID using PreparedStatement.

Error Handling: Catches SQLException and ClassNotFoundException to handle database and driver errors gracefully.

User Interface: A simple console-based menu using Scanner for user input.

Using with PostgreSQL

To use PostgreSQL instead of MySQL:

Replace the JDBC driver with org.postgresql.Driver.

Update the URL to jdbc:postgresql://localhost:5432/employee_db.

Update the database setup SQL for PostgreSQL syntax:

CREATE TABLE employees (
    id SERIAL PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    department VARCHAR(50) NOT NULL,
    salary DOUBLE PRECISION NOT NULL
);


Add the PostgreSQL JDBC driver to your project classpath.

Dependencies:

MySQL Connector/J (for MySQL): mysql-connector-java-<version>.jar



PostgreSQL JDBC Driver (optional, for PostgreSQL): postgresql-<version>.jar
