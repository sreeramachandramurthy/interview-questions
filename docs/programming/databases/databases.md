# Database

A database is an organized collection of structured information (data) stored electronically and optimized for efficient retrieval, insertion, updating, and deletion.

## Basics

1. What is a Database Management System (DBMS)?

    A DBMS is software that manages databases by providing mechanisms to store, retrieve, and manipulate data while ensuring security, consistency, and concurrency control.

    Examples: MySQL, PostgreSQL, MongoDB, Oracle, SQL Server.

2. What are the differences between DBMS and RDBMS

    | DBMS                                      | RDBMS                                     |
    | ----------------------------------------- | ----------------------------------------- |
    | Stores data as files or key-value formats | Stores data in tables (relations)         |
    | No relationships between data             | Supports relationships (PK–FK)            |
    | No normalization rules                    | Follows normalization                     |
    | Examples: File systems                    | Examples: MySQL, PostgreSQL               |

3. What is SQL?

    SQL (Structured Query Language) is a standard language used to interact with relational databases—performing operations like SELECT, INSERT, UPDATE, DELETE, schema creation, and access control.

4. What is a Primary Key?

    A Primary Key (PK) is a column (or set of columns) that uniquely identifies each row in a table.

    Properties:

    - Unique
    - Not NULL
    - One PK per table

5. What is a Foreign Key?

    A Foreign Key (FK) is a column that creates a link between two tables by referencing a primary key in another table. It ensures referential integrity.

6. What is Normalization? Why is it needed?

    Normalization is the process of structuring a database to:

    - Reduce data redundancy
    - Improve data integrity

    Common normal forms:

    - 1NF: Atomic values
    - 2NF: No partial dependency
    - 3NF: No transitive dependency

7. What is Denormalization?

    Denormalization intentionally introduces redundancy to:

    - Improve read performance
    - Reduce complex joins

    Used in OLAP systems or read-heavy workloads.

8. What is ACID?

    ACID properties ensure reliable transactions:

    - Atomicity – all or nothing
    - Consistency – valid state maintained
    - Isolation – transactions don’t interfere
    - Durability – changes persist after commit

9. What are Joins? Explain Types.

    A JOIN combines rows from two or more tables.

    Types:

    - INNER JOIN → matching rows only
    - LEFT JOIN → all left + matching right
    - RIGHT JOIN → all right + matching left
    - FULL OUTER JOIN → all rows from both sides
    - CROSS JOIN → Cartesian product

10. What is an Index? Why is it used?

    An index is a data structure (usually a B-tree) that improves query performance by allowing faster searches.

    Trade-offs:

    - Faster reads
    - Slower writes
    - Uses additional storage

11. Clustered vs Non-Clustered Index

    | Clustered Index                        | Non-Clustered Index                        |
    | -------------------------------------- | ------------------------------------------ |
    | Sorts and stores rows physically       | Logical structure separate from table data |
    | One per table                          | Many per table                             |
    | Faster retrieval by primary key        | Faster retrieval for specific columns      |

12. What is a Stored Procedure?

A stored procedure is a precompiled set of SQL statements stored in the database.
Benefits:

Performance improvement
Reusability
Reduced network traffic
Encapsulated business logic
14. What is a View?

A view is a virtual table created using a SELECT query.
Used for:

Abstraction
Security
Simplifying complex queries
15. What is a Transaction?

A transaction is a unit of work executed in a database that must adhere to ACID properties.

Example:

BEGIN;
UPDATE accounts SET balance = balance - 100 WHERE id=1;
UPDATE accounts SET balance = balance + 100 WHERE id=2;
COMMIT;
16. What is Sharding?

Sharding is the process of splitting data across multiple machines to:

Improve scalability
Handle big datasets

Used in distributed databases like MongoDB, Cassandra.

17. Difference Between OLTP and OLAP
OLTP	OLAP
Online Transaction Processing	Online Analytical Processing
Handles day-to-day operations	Used for analytics, reporting
Small queries, fast response	Complex queries, slower
Highly normalized	Often denormalized
18. What is CAP Theorem?

A distributed system can guarantee only two of the following at the same time:

Consistency
Availability
Partition tolerance

Most NoSQL databases trade off Consistency for Availability.

19. SQL vs NoSQL
SQL	NoSQL
Schema-based	Schema-less
ACID compliant	BASE properties
Vertical scaling	Horizontal scaling
Relational	Document, Key-value, Graph, Wide-column
20. What is a Document Database?

A NoSQL database where data is stored as JSON-like documents.
Examples: MongoDB, CouchDB.
Good for: semi-structured, evolving schemas, hierarchical data.