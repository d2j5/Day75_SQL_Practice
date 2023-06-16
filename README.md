# Day75_SQL_Practice

SQL Query Practice and Database Modification
Due Friday by 11pm Points 100 Submitting a text entry box or a website url
Objective:
The purpose of this assignment is to provide you with hands-on practice with SQL query writing, data insertion, updating, and deleting data from a database.

 

Task:
For this assignment, you will continue working with the 'Bookstore' database and the 'Books' table from the previous assignment. Follow the steps below to complete the assignment:

Insert More Data: Insert five additional books into the 'Books' table.

Query Practice: Write and execute the following SQL queries on your 'Books' table:

Retrieve all books that cost more than $20.
Retrieve all books that were published between 1980 and 2000.
Count the number of books written by each author.
Find the average price of all books in the database.
Modify Data: Write and execute SQL statements to perform the following operations:

Update the price of all books published before 1990, reducing the price by 10%.
Delete all books that were published more than 50 years ago.
 

Reflection:
Write a brief reflection on your experiences with SQL so far. What have you found most challenging? What aspects do you feel confident about? Are there any areas where you still have questions?

 

Submission:
Please submit the SQL queries you wrote for each of the steps above, along with your reflection. Feel free to submit in a repo with a readme for your reflection.

---------------SOLUTION-----------------
-- Task:
-- For this assignment, you will continue working with the 'Bookstore' database and the 'Books' table from the previous assignment. Follow the steps below to complete the assignment:

-- Insert More Data: Insert five additional books into the 'Books' table.
INSERT INTO Books (BookID, Title, Author, PublicationYear, Price) VALUES (6, 'Brave New World', 'Aldous Huxley', 1932, 10.99);
INSERT INTO Books (BookID, Title, Author, PublicationYear, Price) VALUES (7, 'The Adventures of Sherlock Holmes', 'Arthur Conan Doyle', 1892, 8.99);
INSERT INTO Books (BookID, Title, Author, PublicationYear, Price) VALUES (8, 'The Hunger Games', 'Suzanne Collins', 2008, 13.99);
INSERT INTO Books (BookID, Title, Author, PublicationYear, Price) VALUES (9, 'The Shining', 'Stephen King', 1977, 11.99);
INSERT INTO Books (BookID, Title, Author, PublicationYear, Price) VALUES (10, 'The Fault in Our Stars', 'John Green', 2012, 9.99);

-- Query Practice: Write and execute the following SQL queries on your 'Books' table:

-- Retrieve all books that cost more than $20.
SELECT * FROM Books WHERE Price > 20;

-- Retrieve all books that were published between 1980 and 2000.
SELECT * FROM Books WHERE PublicationYear BETWEEN 1980 AND 2000;

-- Count the number of books written by each author.
SELECT Author, COUNT(*) AS BookCount FROM Books GROUP BY Author;

-- Find the average price of all books in the database.
SELECT AVG(Price) FROM Books;

-- Modify Data: Write and execute SQL statements to perform the following operations:

-- Update the price of all books published before 1990, reducing the price by 10%.
UPDATE Books SET Price = (Price - (Price * 0.1)) WHERE PublicationYear < 1990;

SELECT * FROM Books;

-- Delete all books that were published more than 50 years ago.
-- DELETE FROM Books WHERE PublicationYear < (2023 - 50); This is another way.
-- CURDATE() is a function in MySQL that returns the current date in the 'YYYY-MM-DD' format. For example, if today is 2023-06-16, CURDATE() will return '2023-06-16'.
-- YEAR() is a function in MySQL that extracts the year from a date. For example, YEAR('2023-06-16') will return 2023.
-- Then, by doing YEAR(CURDATE()) - 50, you are subtracting 50 years from the current year. Following the previous example, 2023 - 50 would result in 1973.

DELETE FROM Books WHERE PublicationYear < YEAR(CURDATE()) - 50;

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Reflection:

My experience with SQL has been enlightening. I've gained a deeper understanding of data interaction and performing operations through writing SQL queries.

Understanding the syntax and structure of SQL queries was initially challenging. It took time to grasp the clauses, order, and correct usage of keywords and functions. However, with practice and referencing documentation, I've become more comfortable in writing and executing SQL queries.

I now feel confident in retrieving data using SELECT statements and applying conditions and filters for specific results. Writing queries to retrieve information and calculate aggregate functions has become easier.

However, I still have room for improvement. I would like to explore complex joins between multiple tables and enhance my ability to write intricate join queries.

Overall, my experience with SQL has been positive, and I have developed a good foundation in query writing and data manipulation. I am eager to delve into advanced SQL concepts and expand my skills in database management and optimization.

