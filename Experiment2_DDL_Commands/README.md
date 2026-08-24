Experiment 2: DDL Commands
AIM
To study and implement DDL commands and different types of constraints.

THEORY
1. CREATE
Used to create a new relation (table).

Syntax:

CREATE TABLE (
  field_1 data_type(size),
  field_2 data_type(size),
  ...
);
2. ALTER
Used to add, modify, drop, or rename fields in an existing relation. (a) ADD

ALTER TABLE std ADD (Address CHAR(10));
(b) MODIFY

ALTER TABLE relation_name MODIFY (field_1 new_data_type(size));
(c) DROP

ALTER TABLE relation_name DROP COLUMN field_name;
(d) RENAME

ALTER TABLE relation_name RENAME COLUMN old_field_name TO new_field_name;
3. DROP TABLE
Used to permanently delete the structure and data of a table.

DROP TABLE relation_name;
4. RENAME
Used to rename an existing database object.

RENAME TABLE old_relation_name TO new_relation_name;
CONSTRAINTS
Constraints are used to specify rules for the data in a table. If there is any violation between the constraint and the data action, the action is aborted by the constraint. It can be specified when the table is created (using CREATE TABLE) or after it is created (using ALTER TABLE).

1. NOT NULL
When a column is defined as NOT NULL, it becomes mandatory to enter a value in that column. Syntax:

CREATE TABLE Table_Name (
  column_name data_type(size) NOT NULL
);
2. UNIQUE
Ensures that values in a column are unique. Syntax:

CREATE TABLE Table_Name (
  column_name data_type(size) UNIQUE
);
3. CHECK
Specifies a condition that each row must satisfy. Syntax:

CREATE TABLE Table_Name (
  column_name data_type(size) CHECK (logical_expression)
);
4. PRIMARY KEY
Used to uniquely identify each record in a table. Properties: Must contain unique values. Cannot be null. Should contain minimal fields. Syntax:

CREATE TABLE Table_Name (
  column_name data_type(size) PRIMARY KEY
);
5. FOREIGN KEY
Used to reference the primary key of another table. Syntax:

CREATE TABLE Table_Name (
  column_name data_type(size),
  FOREIGN KEY (column_name) REFERENCES other_table(column)
);
6. DEFAULT
Used to insert a default value into a column if no value is specified.

Syntax:

CREATE TABLE Table_Name (
  col_name1 data_type,
  col_name2 data_type,
  col_name3 data_type DEFAULT 'default_value'
);
Question 1
Q1
ALTER TABLE Student_details ADD COLUMN State TEXT;
Output:

QA1
Question 2
Q2
CREATE TABLE Departments(
DepartmentID INTEGER,
DepartmentName TEXT);
Output:

QA2
Question 3
Q3
CREATE TABLE item(
item_id TEXT PRIMARY KEY,
item_desc TEXT NOT NULL,
rate INTEGER NOT NULL,
icom_id TEXT(4),
FOREIGN KEY (icom_id) REFERENCES company(com_id)
ON UPDATE CASCADE
ON DELETE CASCADE);
Output:

QA3
Question 4
Q4
CREATE TABLE products(
product_id INTEGER PRIMARY KEY,
product_name TEXT NOT NULL,
list_price DECIMAL(10,2) NOT NULL,
discount DECIMAL(10,2)NOT NULL
DEFAULT 0,
CHECK (list_price >= discount),
CHECK (list_price >= 0),
CHECK (discount >=0 )
);
Output:

QA4
Question 5
Q5
INSERT INTO Employee (EmployeeID,Name,Position,Department,Salary) VALUES(001,'Sarah Parker','Manager','HR',60000);
Output:

QA5
Question 6
Q6
INSERT INTO Customers (CustomerID,Name,Address,City,ZipCode) VALUES(302,'Laura Croft','456 Elm St','Seattle','98101');
INSERT INTO Customers (CustomerID,Name,Address,City,ZipCode) VALUES(303,'Bruce Wayne','789 Oak St','Gotham','10001');
Output:

QA6
Question 7
Q7
CREATE TABLE item(
item_id TEXT PRIMARY KEY,
item_desc TEXT NOT NULL,
rate INTEGER NOT NULL,
icom_id TEXT(4),
FOREIGN KEY (icom_id) REFERENCES company(com_id)
ON UPDATE SET NULL
ON DELETE SET NULL);
Output:

QA7
Question 8
Q8
CREATE TABLE contacts(
contact_id INTEGER PRIMARY KEY,
first_name TEXT NOT NULL,
last_name TEXT NOT NULL,
email TEXT,
phone TEXT NOT NULL,
CHECK(LENGTH(phone)>=10)
);
Output:

QA8
Question 9
Q9
ALTER TABLE student_details
ADD COLUMN Date_of_birth Date;
Output:

QA9
Question 10
Q10
INSERT INTO Student_details (RollNo,Name,Gender,Subject,Marks)
SELECT RollNo,Name,Gender,Subject,Marks
FROM Archived_students;
Output:

QA10
RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
