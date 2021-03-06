# Homework 2

* Assigned: 2/18
* Due: 3/4 10:00AM
* Worth 3.75% of your grade
* Done and submitted individually (as with all the homeworks) **via [Gradescope](https://www.gradescope.com)**. 
Please assign the correct pages to the different questions; failure to do so may be penalized.

### Changelog
* 2/21: For join between two tables with the same attribute name, please assume that the join result will change the ambiguous column names to be tablename.attributename. For example, the join between Person(**ssn**, companyid, salary, managerid) and Company(**companyid**, companyname, location) on companyid will have schema (ssn, Person.companyid, salary, managerid, Company.companyid, companyname, location).

* 2/28: Problem 3.3 has been updated because the division operator is not taught in class. For problem 1, aggregation has been **disallowed** for relational algebra. The Overleaf latex template has been updated for relational algebra symbols allowed.

* 3/2: HW2 won't accept submission after 3/5 10:00 AM EST because we will release solution on 3/5.

## Submission

1. You will write your answers using the [following Overleaf latex template](https://www.overleaf.com/read/mvhfmrqpnqbs). Clone the template and edit it.   Hand writing or alternative submission formats are NOT accecptable.
2. You will then submit the compiled PDF on GradeScope


## 1. Relational Algebra

**(2 points each, 6 points total)**

Consider the simplified Employee Stock Ownership Database below (primary keys are in **bold**):

* Person(**ssn**, companyid, salary, managerid)

This is an employee table. *companyid* is a foreign key which points to *Company*.
We assume one employee can only work at one company. *managerid* is a foreign key
which points to another *Person* record .

* Company(**companyid**, companyname, location)

* Holding(**ssn**, **companyid**, sharenum)

Holding table describes an employee(*ssn*) owns *sharenum* stocks of *companyid*.

Construct relational algebra for the following queries:

* **Q1**: Find the *ssn* of the persons who work at Google(*companyid* = 601) and hold more than 500 *sharenum*
   of stock from Facebook(*companyid* = 700).

* **Q2**: Find the *ssn* of the persons whose stocks are all different from those his/her manager owns.
    (Note: Each *companyid* represents a different stock, we do not care about the *sharenum* of stocks).

* **Q3**: Find the *ssn* of the persons who own at least three different stocks.


## 2. More Relational Algebra

**(2 point each, 12 points total)**

T1

|A | B | C |
|---|---|---|
|1 | x | a |
|2 | y | c |
|2 | y | b |
|2 | z | c |


T2

B | C | D
---|---|---
1 | x | c
2 | y | c
3 | x | a


Write the result table for the relational algebra expressions in a similar with T1 and T2:

Note: Here, we assume the attributes whose values are all numbers are the same type: integers
and all the letters are the same type: char. If the result table is empty, write the schema of the table.


1. ??<sub>A,B</sub>(T1)

2. ??<sub>D</sub>(T2)

3. T1 ?? ??<sub>A</sub>(T1)

4. T1 ???<sub>T1.B=T2.C</sub> T2

5. T1 ??? (T1 ??? T2)

6. T1 ???<sub>T1.A&gt;T2.B</sub> (??<sub>B&ne;2</sub>(T2))


## 3. SQL

**(2 points each, 6 points total)**

Here are three relationship, (primary keys are in **bold**):

* Store(**storeid**, s_name, employee_number, city)

* Goods(**g_id**, g_name, price)

* Supply(**storeid**, **g_id**)

### Requirements:

First, describe the meaning of following relational algebra expressions in one or two sentences.
Second, translate the following relational algebra expressions in SQL. Make sure your SQL can be executed.


1. ??<sub>storeid, s_name</sub>(??<sub>employee_number<=100 or city = "New York"</sub>(Store))

2. ??<sub>s_name</sub>(((??<sub>g_name = "pencil"</sub>Goods) ??? Supply) ??? Store)

3. ??<sub>storeid</sub>(Store) ?? ??<sub>g_id</sub>(Goods) - Supply
