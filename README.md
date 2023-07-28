# Que 1 : Give examples of primary key and composite primary key and foreign key.

# Primary Key: A primary key is a unique identifier for each record (row) in a database table. It ensures that each row can be uniquely identified and allows for efficient data retrieval and linking between tables. A primary key column must have unique values, and it cannot contain NULL values.

Let's say we have a table named "Students" with the following columns:

StudentID (Primary Key)
Name
Age
Gender

The "StudentID" column would be the primary key in this table. It uniquely identifies each student in the "Students" table.

Composite Primary Key: A composite primary key is a primary key that consists of two or more columns in a table. The combination of these columns must be unique for each record. This is useful when no single column can uniquely identify a row, but a combination of columns can do so.

Let's consider a table named "Orders" with the following columns:

OrderID
ProductID
Quantity
OrderDate

In this case, the combination of "OrderID" and "ProductID" could form the composite primary key. This ensures that each order for a specific product is unique in the "Orders" table.

# Foreign Key: A foreign key is a column or a set of columns in a table that refers to the primary key of another table. It establishes a link or relationship between two tables, enforcing referential integrity. A foreign key in one table is used to reference the primary key in another table.

Continuing from the "Orders" table example, let's say we have another table named "Products" with the following columns:

ProductID (Primary Key)
ProductName
Price

Now, in the "Orders" table, the "ProductID" column would be the foreign key, referencing the "ProductID" column in the "Products" table.


# Que 2 : Make a table named User which will have the following fields
Username
Email
First Name
Last Name
Phone No
Address
HSC Result
Date of Birth
Age
password

# Ans 2 :
 CREATE TABLE User (
    		Username VARCHAR(50),
    		Email VARCHAR(100),
    		First_Name VARCHAR(50),
    		Last_Name VARCHAR(50),
    		Phone_No VARCHAR(20),
    		Address VARCHAR(200),
    		HSC_Result DECIMAL(5, 2),
    		Date_of_Birth DATE,
    		Age INT,
    		Password VARCHAR(100)
);

# Que 3 : Write proper constraints of question no 4 and create table.

CREATE TABLE User (
    	Username VARCHAR(50) NOT NULL,
    	Email VARCHAR(100) NOT NULL,
    	First_Name VARCHAR(50),
    	Last_Name VARCHAR(50),
    	Phone_No VARCHAR(20),
    	Address VARCHAR(200),
    	HSC_Result DECIMAL(5, 2),
    	Date_of_Birth DATE,
    	Age INT CHECK (Age >= 0),
    	Password VARCHAR(100) NOT NULL,
    	PRIMARY KEY (Username),
    	UNIQUE (Email)
);

# Que 4 : Write the disadvantages of redundancy and incompleteness in database design.

# Disadvantages of Redundancy in Database Design:

1. Wasted Storage: Redundancy leads to the storage of the same data multiple times in the database. This unnecessarily increases the size of the database and wastes storage space, impacting overall performance and increasing maintenance costs.

2. Inconsistency: Redundant data can cause inconsistencies when the same information is updated in one place but not in others. This can lead to conflicting or outdated data, resulting in data integrity issues and inaccurate query results.

3. Data Anomalies: Redundancy can cause anomalies during data manipulation. For example, if data is duplicated, updating one occurrence of the data while leaving the others unchanged may result in inconsistencies.

4. Increased Complexity: Maintaining redundant data adds complexity to the database design and makes it harder to ensure data integrity and consistency across the system.

5. Difficulty in Updating: When redundant data exists in multiple places, updating the data requires making changes in all occurrences, which can be error-prone and time-consuming.

# Disadvantages of Incompleteness in Database Design:

1. Data Integrity Issues: Incomplete data may violate integrity constraints or business rules, leading to incorrect results or system behavior.

2. Inaccurate Reporting and Analysis: Incomplete data can lead to inaccurate reports and analysis, making it difficult for users to make informed decisions based on incomplete or missing information.

3. Limited Functionality: Incomplete data may prevent certain functionalities from working correctly, hindering the overall system's capabilities and user experience.

4. Loss of Historical Information: Incompleteness can lead to the loss of historical data, making it challenging to analyze trends or track changes over time.

5. Inefficient Data Retrieval: When data is incomplete, more complex queries may be required to retrieve meaningful information, resulting in slower query performance.

6. User Frustration: Incomplete data can frustrate users who rely on the system for accurate and comprehensive information, leading to decreased user satisfaction.

# Que 5 :  From HR Database, Select the employee who has last name starts with “k” or ends with “k”

SELECT *
FROM employees
WHERE last_name LIKE 'k%' OR last_name LIKE '%k';

# Que 6 : From HR Database Select the employee who gets more salary than his/her manager.

SELECT e.*
FROM employees e
JOIN employees m ON e.manager_id = m.employee_id
WHERE e.salary > m.salary;

# Que 7 : From HR Database, print all the employee names along with department names.

SELECT e.first_name, e.last_name, d.department_name
FROM employees e
JOIN departments d ON e.department_id = d.department_id;



