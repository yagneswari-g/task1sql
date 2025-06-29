# Task 1: Library Database Schema

##  Objective

Design and implement a relational database schema for a **Library Management System** using SQL. This includes identifying entities, defining relationships, applying normalization, and using appropriate keys and constraints.

---

##  Domain: Library Management System

This project models the core data entities and relationships in a typical library:

- Books
- Authors
- Publishers
- Members
- Book Loans

---

##  ER Diagram


> The ER diagram illustrates the relationships between entities such as Books, Authors, Publishers, Members, and Loans using proper foreign key connections.
Entities:

Book: BookID (PK), Title, Genre, PublisherID (FK), YearPublished

Author: AuthorID (PK), Name, Country

BookAuthor: BookID (FK), AuthorID (FK) → Composite PK

Publisher: PublisherID (PK), Name, Contact

Member: MemberID (PK), Name, Email, JoinDate

Loan: LoanID (PK), BookID (FK), MemberID (FK), IssueDate, ReturnDate

Relationships:

Book–Publisher: Many-to-One

Book–Author: Many-to-Many (via BookAuthor)

Book–Member (Loan): Many-to-Many

---

##  Entities and Relationships

| Table        | Description |
|--------------|-------------|
| **Books**     | Contains information about each book |
| **Authors**   | Contains details of book authors |
| **BookAuthors** | A join table for many-to-many relationship between books and authors |
| **Publishers** | Stores publisher info |
| **Members**   | Library members who borrow books |
| **Loans**     | Records of which member borrowed which book and when |

---

##  Keys and Constraints

- **Primary Keys**: Auto-incremented integer IDs for all major entities.
- **Foreign Keys**: Used to enforce referential integrity between related tables.
- **Composite Keys**: Used in the `BookAuthors` table to handle many-to-many relationships.
- **Constraints**: `NOT NULL`, `UNIQUE`, and `AUTO_INCREMENT` where appropriate.

---

##  Tools Used

- **MySQL Workbench** – for schema creation
- **GitHub** – for code sharing and version control

---

##  SQL Features Demonstrated

- `CREATE DATABASE`
- `CREATE TABLE` with constraints
- `PRIMARY KEY`, `FOREIGN KEY`, `AUTO_INCREMENT`
- Composite keys for many-to-many relationships
- Referential integrity using foreign keys

---

##  Normalization

The schema is normalized to **Third Normal Form (3NF)**:
- Elimination of repeating groups (1NF)
- No partial dependencies (2NF)
- No transitive dependencies (3NF)

---


