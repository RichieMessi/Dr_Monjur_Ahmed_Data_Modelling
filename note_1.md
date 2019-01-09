# Database Modelling Udemy Course

> ## Learning Objectives 
## Understand...
* ## Database and Relational Database
* ## Data Modelling 
* ## Entitiy Relationship Diagram (ERD)
* ## Design Database
* ## Analyze business/organization to model data requirement

---
>## Course Outline
* ### database ? Relation Database ?
* ### tables?
* ### Anomalies (Insert, Update, Delete)
* ### Case Study Analysis (real life scenario analysis)
* ### Database Development Steps (Conceptual, Logical, Physical)
* ### Entity Relationship Deagram (ERD)
* ### Dependency (Functional, Partial, Transative)
* ### Normalization (UNF, 1NF, 2NF, 3NF)


---
>## Acquired Skills after course completion
* ### Data Modelling
* ### Relational Database Design

---

># __What is a Database ?__

* ## Where we keep data
* ## Keeping data without planning is problematic
* ## Need a specific structure to organize data - TABLES

>## __Students Table__
| StudentID | Name          |      Address     |
| ----      | -----         |      -------     |
| 1         | JohnDoe       |      Hamilton    |
| 2         | MaryJane      |      Mississauga |
| 3         | JohnDoe       |      Hamilton    |
| 4         | MaryJane      |      Mississauga |

## Vertical section = column = __*Domain*__ bcoz only one type of data exists in this section
## Horizontal section = row =  __*Record*__ bcoz data in this section belongs to only one student 

* ## Table is a collection of rows and columns or a collection of records and domains
* ## Database is a collection of tables


> ## Difference between Relational Database and a Database ?

* ## Database
    * ### A random collection of tables
* ## Relationanl Database
    * ### Not random collection. The tables have a relation or a connection in between each other


> ## Why Relational Database 

## Table 1 - Admissions Department
| ID |  Name    | Address   |
| -- |  ----    |  -------  |
| 1  |  John    | New York California  |
| 2  |  Mary    | New Jsy   |
| 3  |  Rich    | Toronto   |
| 4  |  Jake    | Greenland |

* ## In the tables 1 and 2
    * John has two different addresses.  John can have two different databases
    * Primary Address and Secondary Address
    * However - The address is different in two different tables
    * This implies that this is not an example of a relational database
    * Something is clearly wrong with this design
    * Lets say John used to live in California at first but then moved to CANADA, after some years we query the database, how can I know which one is the correct address when a record shows two different addresses. This creates a problem
    * This is one reason why we make a relational database
## Table 2- Accounts Department
| ID |  Name    | Address   |       Fees    |   Paid    | Due   |
| -- |  ----    |  -------  |       ------- | -------   | ------|
| 1  |  John    | New York Canada|  1000    |   300     |  700  |
| 2  |  Mary    | New Jsy   |       1500    |   500     |  1000 |
| 3  |  Rich    | Toronto   |       1200    |   1000    |   200 |
| 4  |  Jake    | Greenland |       1000    |   400     |   600 |

> # NOW here is how a relational database would look like. This is not a good database design however, this shows how a duplicate address problem that we saw above can be rectified


## Table 1 - Admissions Department
| ID |  Name    | Address   |
| -- |  ----    |  -------  |
| 1  |  John    | New York California  |
| 2  |  Mary    | New Jsy   |
| 3  |  Rich    | Toronto   |
| 4  |  Jake    | Greenland |

* ## In the tables 1 and 2
    * Now address is just in one table, Addmissions Table has to use the primary key of Accounts Department to inquire a students address. 
    * There is only one table that has address. Therefore, there is no redundancy
    * This design still has problems that we will fix as we go further. 
    * For the meantime, this  solves the mistaching problem of the address
    * In both tables, every record in both tables is linked to each other through an ID. Both records in two tables with common ID are linked to each otehr through the ID. 
## Table 2- Accounts Department
| ID |  Fees    |   Paid    | Due   |
| -- |  ------- | -------   | ------|
| 1  |  1000    |   300     |  700  |
| 2  |  1500    |   500     |  1000 |
| 3  |  1200    |   1000    |   200 |
| 4  |  1000    |   400     |   600 |

> ### Somehting like this...

<!-- ![markdown Logo](./images/key_relation.png) -->

> ## Every row in a database musy have a unique identifier
* ## This has to be unique to avoid the same problem we saw above.
 ## *Redudancy* is *bad* coz its leads to confusion 😋😋😋 . 
 * Names cannot be used as a unique identifier as people can have unique names
 * We cannot ask people to change their names coz we need to add them to a database lol. That would suck 😢 😢 😢