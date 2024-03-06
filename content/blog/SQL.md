+++
title = "My second post"
date = 2019-11-28
+++

# SQL
Docs [mariadb](https://www.mariadbtutorial.com/mariadb-basics/)

### OSI Layers

| No.     | Layers      |
| :-------| :--------:  |
| Layer 7 | APPLICATION |
| Layer 6 | PRESENTATION|
| Layer 5 | SESSION     |
| Layer 4 | TRANSPORT   |
| Layer 3 | NETWORK     |
|  Layer 2| DATA LINK   |
| Layer 1 | PHSYICAL    |


### Database

Organized collection of data,stored and retrieved digitally from remote or local computer.

### DBMS

Responsible for updating ,retrieval,creating and management of the databases. It ensures the our data is consistent(meaning the data in our database is valid by follwing a set of rules), organized and the retrieval of the data is easily available for users or software application.

### RDMS

It's a system for managening the databases.

### SQL

Structured Query Language.Which is used for manipulating and retrieving databases.

### MySQL

Relational Database Management System.Which is used for management of the databases.

### What is Transaction?
- Transaction in simple words is a group of queries.
- In Technical Terms, it's a group of database read and write operations that will only succeed when the operations(i.e queries) within it succeed.

### ACID
---
ACID Transaction make sure that data will be consistent after queries or group of queries(Transaction) is executed.
- A(Atomicity)
  - Atomitciy means that transaction can either be successfull or fail means there will be nothing in between like either half successfull or fail.
  - It also guarantees that all the commands that make a transaction are treated as single unit.
- C(Consistency)
   - Consistency means that the changes made within a transaction  are consistant with database constraints. This includes rules,constraints and triggers which are put on the database by the user will remain unchanged.
- I(Isolation)
  - Isolation guarantees that all transaction will run in an isolated environment so that other transaction will not affect each other.
D(Durability)
  - Durability guarantees that once the transaction completes and changes are written to the database , they are presisted.
  - This ensures that data will be persisted even in case of system failures like crashes or power outages.


### Basics


#### 1. SELECT Clause/statement

-------------------
It is used to retrieve data from one or more tables. It can be uses with various options to make complex queries.
SELECT select_list from table_name; -- even though SELECT statement appears before the from clause , the from clause gets executed or evaluated first then SELECT gets evaluated.
SELECT statement return a set of result rows which is also called as result set.

#### 2. ORDER BY Clause
-----------------------------
```
select
    select_list
from
    table_name
order by
    sort_expression1 [asc | desc],
    sort_expression2 [asc | desc],
    ...;
```
there can be multiple sort_expressions
sort_expression can be either column or expression by which you want to order, then use ASC or DESC
ORDER BY uses ASC by default
ORDER BY can be use to sort the rows of result set by values in one or more columns in ASC or DESC
**The Clause evaluation happens like ==> FROM --> SELECT --> ORDER BY**


#### 3. WHERE Clause
-----------------------------

```
select
    select_list
from
    table_name
where
    search_condition
order by
    sort_expression;
```
WHERE is an optional clause for SELECT
WHERE gives search condition for selection rows
We can use WHERE statement in DELETE and UPDATE statment to specify the row to delete or update.
Mariadb evaluates the clauses as FROM --> WHERE --> SELECT --> ORDER BY

### Operators
--------
1. =
2. and
3. or
4. comparision operator
5. between
6. in
7.  like -- expression LIKE pattern
It return true if a values matches the pattern.<br>
Patterns :-
    1. %matches one or more characters
    2. _matches one character

----------
<br>

#### 4. DISTINCT Clause
---------------------------
```
select
    distinct column_name
from
    table_name;
```
It is used to remove duplicates rows from the result set by using the values in the column for distinction.
It can also be applied to multiple column_names
```
select
    distinct column_name1, column_name2....
from
    table_name;
```

### Operators

#### 1. BETWEEN
--------------------
```
expression between low and high.
```
expression can be expression or column_name
It's a logical orperator which return a value between two values.
It's typically used in WHERE Clause to form search condition.
To negate BETWEEN we can use NOT operator
NOT BETWEEN -- return value if the values is not between two values.

#### 2. LIKE
------------------

It is used for searching a string that matche a specific pattern.
Pattern inclueds regular characters and special characters. Special characters are wild cards.
There are 2 wildcards '%' and '_'
* The percent wildcard (%) matches any string of zero or more characters.
* The underscore (_) wildcard matches any single character.
It is used in the `where` clause of the `select`, `update` and `delete` statement so it can filter rows based on pattern.

To match all the string that start with d use `d%`
To match all the string that end with d use `%d`
To match all the string that contain with state use `%state%`

Suppose If a value contains special character then use backslash `\` to escape it.

```
select 'v_2019' like '%\_%20';

```
The above statement will return 1 because in 'v_2019' contains  `_20` . we check by using `%...%`. In here we escape the `_` special character which is included in `_20`.

#### 3. IN
-------

It compares a value with the list of values

```
expression IN (v1, v2, v3, ...)
```
The value list can be a comma-separated list of literal values or a result set of another select statement.
```
expression in (select-statement)
```
The in operator is often used in the where clause of the select, delete, and update statements.

#### 4. LIMIT
----------

It allow you to specifies the number of rows returned by the SELECT statement.
As we know that `SELECT` statement returns a row of result in unspecified order, so it's good practise to use `limit` clause with `order by ` always.

```
select select_list
from tale_name
order by sort_expression
limit n [offset m];
```
offset `m` is used to skip the first `m` rows and print out the next `n` rows.


#### 5. Is Null
----------
Null Indicates that a values is missing , unknown or inapplicable value.
**Null does not equal to any value , even itself.**

```
expression is null

```

**IS NOT NULL**
```
value is not null

```
`IS NOT NULL` will return true if the value is not null and false if the value is null.

As we know `0` means false and `1` means true.
In sql `0` is not null '''' and `''` empty string is not null and `null` is null itself.
You can check by following the below syntax.
```
select 0 is null, '' is null, null is null;
```
For `0` and `''` empty string it will return 0 . For `null` it will return 1.

#### 6. JOIN Clause
----------

To retrieve a data from multiple tables we use `JOIN` clause with `SELECT` statement.
`JOIN` clause associate(get together) rows from one table with the rows from another tables using a particular(specific) condition.

Types of `JOIN`
  - inner join
  - left join
  - right join
  - cross join

**Mariadb doesn't support full outer join or full join.**

- INNER JOIN
----------

`inner join` syntax for joining two tables.

```
select select_list
from t1
inner join t2
    on join_condition;
```

`inner join` compares each row from the table `t1` with every row from the table `t2`.
if values of the row causes the join_condition to return true . then, `inner join` will create a new row with columns that contains the columns , from the both the tables , specified in select_list(columns) , includes it in this new row in the result set.

Typically , we use `=` operator to match the rows from the table `t1` with the table `t2`.

```
select select_list
from t1
inner join t2
    on t2.column1 = t2.column2;

```

Suppose ,if both the tables have same column name then ,we can use `using` clause.

```
select select_list
from t1
inner join t2 using (column);

```

To join three or more tables . We can use the following syntax.

```
select select_list
from t1
inner join t2 on join_condition2
inner join t3 on join_condition2
...;

```
Here, This can happen that if the t1 doesn't have the column for t3 table for checking of join_condition2 then it will look in the t2 table if it exists.

#### illustration of inner join

![Diagram](https://www.mariadbtutorial.com/wp-content/uploads/2019/10/MariaDB-join-inner-join.png)

- LEFT JOIN
----------

Left join introuduces the left and righ tables.
Syntax is similar to the `inner join` just replace it with left join
`left join` retrives the data from the left table. It will compares each row from the left table with the right table.
If the on condition return true then it will creates a new row whose columns includes the columns for the rows from both the tables speciefied by the select_list.
If the on condition return false then also it will creates a new row whose columns includes the columns of the row from the left table and null values for columns of the row from right table .
Simply put, the left join retrieves all rows from the left table (t1) whether they have matching rows from the right table or not.


#### illustration of LEFT JOIN

![Diagram](https://www.mariadbtutorial.com/wp-content/uploads/2019/10/MariaDB-join-left-join.png)


- RIGHT JOIN
----------

`RIGHT JOIN` is the reverse of the `LEFT JOIN`.
Syntax is also similar just replace `LEFT JOIN` with `RIGHT JOIN`

#### illustration of RIGHT JOIN

![Diagram](https://www.mariadbtutorial.com/wp-content/uploads/2019/10/MariaDB-join-right-join.png)

- CROSS JOIN
----------
The `cross join` combines each row from t1 table with every row from the t2 table to form the result set.

Syntax is also similar just replace `RIGHT JOIN` with `CROSS JOIN` and it doesn't need on condition.

### Storage
----
- Storage engines  handle the data at the physical level. Storage engines are designed to manage the data files, the data and the index caches efficiently.
- Mariadb use InnoDB as Storage Engine. Previously it used Aria.
- To show the current engine.

 ```sql
 select @@global.storage_engine;
 ```



