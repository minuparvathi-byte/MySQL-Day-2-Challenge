# MySQL-Day-2-Challenge
This project is part of my MySQL learning journey as I prepare for a career in Data Analytics.
The Day 2 Challenge focuses on practicing SQL operations such as:

Creating tables with constraints
Inserting records into tables
Retrieving data using SELECT
Updating records using UPDATE
Applying constraints like:

**PRIMARY KEY**

**NOT NULL**

**UNIQUE**

**CHECK**

**DEFAULT**

The challenge helps in understanding how databases maintain data accuracy and integrity while performing real-world operations.

**Overview**

This project demonstrates basic SQL database operations using MySQL.
It includes creating a database table, applying constraints, inserting sample records, retrieving data, and updating records while maintaining data integrity.

Topics Covered
Database creation
Table creation
SQL Constraints
Insert statements
Select queries
Update queries
Data validation
SQL Concepts Used
**CREATE DATABASE
CREATE TABLE
INSERT INTO
SELECT
UPDATE
CHECK Constraints
PRIMARY KEY
NOT NULL
UNIQUE**

Challenge Tasks

**1. Create Table**

Created a table with appropriate constraints to ensure valid data storage.

**2. Insert Records**

Inserted multiple records into the table while following all constraints.

**3. Retrieve Data**

Used SELECT statements to verify inserted records.

**4. Update Records**

Updated specific values like price or quantity while maintaining constraint rules.

**Expected Outcome**

All records are inserted successfully

Constraints prevent invalid data entries

Updated records display correctly

Data integrity is maintained

Tools Used

MySQL

MySQL Workbench

**Learning Outcome**

Through this challenge, I improved my understanding of:

SQL query writing

Database constraints

Data management operations

Practical database handling skills useful for Data Analytics


-- create the database

create database online_bookstore;

use online_bookstore;

-- creating books table

create table Books(

	Book_id int primary key,
  
    Title varchar(100) not null,
    
    Author varchar(50) not null,
    
    ISBN varchar(20) unique,
    
    Price decimal(8,2) check(price>0)
    
);

-- creating orders table

create table Orders(

	Order_id int primary key,
  
    Book_id int,
    
    Orderdate date not null,
    
    Quantity int check(quantity>0),
    
	foreign key (Book_id) References Books(Book_id)
  
    );

-- alter table

alter table Books

modify ISBN varchar(20) default 'Not Available';

-- Insert records into Books table

INSERT INTO books(Book_id, Title, Author, ISBN, Price)

VALUES

(1, 'SQL Basics', 'Nidharsana', 'ISBN101', 450.00),

(2, 'Python Guide', 'Harini', 'ISBN102', 550.00),

(3, 'Power BI Essentials', 'Saranya', 'ISBN103', 700.00),

(4, 'Data Analytics', 'Parvathi', 'ISBN104', 650.00),

(5, 'Machine Learning', 'Jeevanthika', 'ISBN105', 900.00);


-- Insert records into orders table 

Insert into orders

values (001, 1, '2026-01-31', 5),

	   (002, 5, '2026-02-02', 2),
     
       (003, 3, '2026-02-05', 1),
       
       (004, 2, '2026-02-25', 4);
       
-- Retrieve all records

select * from books;

--  update a price in books table

update books

set price=600 

where Book_id=2;


select*from orders;

-- update a quantity in orders table 

update orders

set quantity=7

where order_id=3;


-- delete a row

delete from orders

where order_id=003;

-- delete a row

delete from books

where price<500;

-- truncate the table

truncate table books;

MySQL Day 2 Challenge – Online Bookstore Database

**Project Description**

This project is a part of my MySQL practice for improving database management skills required in Data Analytics.
The challenge focuses on creating and managing an Online Bookstore Database using MySQL.


The goal of this challenge is to understand how relational databases work while maintaining data integrity using constraints like PRIMARY KEY, FOREIGN KEY, NOT NULL, UNIQUE, CHECK, and DEFAULT.

Author

**Minu Mohan**

Aspiring Data Analyst | Learning SQL, Excel, Power BI & Python





