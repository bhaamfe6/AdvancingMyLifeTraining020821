# Intro-To-SQL
SQL stands for *Structured Query Language* and is the language used to interact with relational databases - and, increasingly, non-relational databases as well. it is a set of statements with which all programs and users access data. ***Relational Database Management System (RDBMS)*** is <u>the basis for SQL</u>, and for all modern databases systems such as MS SQL Server, IBM DB2, Oracle, MySQL, and Microsoft Access.

The data in **RDBMS** is stored in <u>database objects</u> called *tables*. A `table` is a `collection of related data` entries and it consists of columns and rows.

ALthough there are different versions of SQL, to be compiant with ANSI standard, they all support at least the major commands (SELECT, UPDATE, DELETE, INSERT, WHERE) in similar manner.


## Key SQL Features:
- SQL can:
    1. Execute queries against a database
    2. Retrieve data from a database
    3. Insert records in a database
    4. Update records in a database
    5. Delete records from a database
    6. Create new databases
    7. Create new tables in a database
    8. Create stored procedures in a database
    9. Create views in a database
    10. Set permissions on tables, procedures. and views
    ![Referene from w3schools.com](https://www.w3schools.com/sql/sql_intro.asp)


![Introduction to SQL Course by Datacamp.com](http://campusdatacamp.com/courses/introduction-to-sql.html)

SQL can be used to create and modify databases and querying databases.  A query is a request for data from a database table (or combination of tables). Querying is an essential skill for a data scientist, since the data you need for your analyses will often live in databases.

In SQL you can select data from a table using a `SELECT` statement.
- ***For Example*** - 
`SELECT name FROM people;`

In this query, `SELECT` and `FROM` are called keywords.  In SQL, keywords are not case-sensitive, which means you can write the same query as follows:

`select name from people;`

That said, it's good practice to make SQL keywords uppercase to distinguish them from other parts of your query, like colmn and tables names.

It is also good practice to include semicolon at the end of your query.  This tells SQL where the end of your query is.

##SELECTING MULTIPLE COLMNS
SQL makes selecting multiple columns easy. To select multiple colmns from a table, simply separate the column names with commas.

***For example, this query selects two columns, `name` and `birthdate` from the `people` table:

`SELECT name, birthdate FROM people;`

Sometimes, you may want to select all columns from a table. Typing out every column name would be a pain, so there's a handy shortcut:

`SELECT * FROM people;`

If you only want to return a certain number of results, you can use the `LIMIT` keyword to limit the number of rows returned:

`SELECT * FROM people LIMIT 10;`

##SELECT DISTINCT
If your results include duplicate values, and you want to select all the unique values from a column, you can use the `DISTINCT` keyword
- ***For Example:***

`SELECT DISTINCT language FROM films:`

***<u>NOTE- It is important to know the exact and correct field, column, and table name!</u>***

## COUNTING
If you want to count, the COUNT statement lets you do this by returning the number of rows in one or more columns.

***For example*** 
- The following code gives the number of rows in the `people` table:

`SELECT COUNT(*) FROM people;`

If you want to count the numbere of non-missing values in a particular column, you can call COUNT on just that column with:
    `SELECT COUNT(birthdate) FROM people;`
In the above example, `birthdate` represents the column fieldname, of course.
It's also common to combine `COUNT` with `DISTINCT` to count the number of *distinct* values in a column.

***For example*** - 

`SELECT COUNT(DISTINCT birthdate) FROM people;`

## SYNTAX EXAMPLES FROM 
![SQLZoo.net](https://sqlzoo.net/wiki/SELECT_basics)

This example uses a WHERE clause to show the population of 'France'. The string is in single quotes.

`SELECT population FROM world WHERE name = 'France';`

The following example checks a list using the keyword IN, which allows us to check or retrieve data from certain list of items.  The example shows name and population for the countries 'Brazil', 'Russia', 'India', and 'China'.

`SELECT name, population FROM world WHERE name IN ('Brazil', 'Russia', 'India', 'China');`

The keyword BETWEEN allows range checking of specified inclusive boundary values.  The example below shows countries with an area of 250,000 - 300,000 sq km.

`SELECT name, area FROM world WHERE area BETWEEN 2500000 and 300000;`

- **MORE SYNTAX EXAMPLES:

`SELECT name, population FROM world WHERE name LIKE 'Al%';`

Produces all countries that begin with the letters "Al".

`SELECT name FROM world WHERE name LIKE '%a' OR name Like '%l';`
Produces results that show all names that end in "a" or "l".

`SELECT name, length(name) FROM world WHERE length(name) = 5 and continent = 'Europe';`

Produces results from the World table and the name and length(name) columns with countries on the Europe continent whose name lengths are 5 characters long.

Angle brackets can also be used to show range. For example:

`SELECT name, area, population FROM world WHERE area > 50000 AND population < 1000000;`

You can also do calculations as in determining population density which is density population = population/area.

`SELECT name, population/area FROM world WHERE name IN ('China', 'Nigeria', 'France', 'Australia');`

To simply retrieve all data (columns with field names, and rows) 

`SELECT * FROM customers;`

In the above example the (*) request all data from table name "customers".

The NOT keyword can be used to exclude data for example:

`SELECT * FROM Customers WHERE NOT city = 'Berlin';`

Request to retrieve records where the City is NOT 'Berlin'.

To sort or ORDER all data in a table's specified column alphabetically use

`SELECT * FRFOM customer ORDER BY city;`

Reverse order would be...

`SELECT * FROM customers ORDER BY city DESC;`

To order multiple columns list the columns and separate them with ",".

`SELECT * FROM customer ORDER BY city, population;`

To insert a new record in a table...

`INSERT INTO customer ( CustomerName, Address, City, PostalCode, Country) VALUES ('Hekkan Burger, 'Gateveien 15', 'Sandnes', '4306', 'Norway');`

This example inserts a new record into a table named customer.  The fields have been specified and the data for each field has been specified.

