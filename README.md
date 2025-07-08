# 📚 Library Management System

This Library Management System is an academic project designed to demonstrate effective database design and implementation using ER diagrams, relational modeling, and normalization techniques. It supports essential library functions like managing books, tracking authors and publishers, issuing loans, and managing librarians and members.

---

## ✅ Key Highlights

- 📘 **Book Management:** Add, update, and manage book details.
- 👤 **Author & Publisher Tracking:** Maintain data about book authors and publishers.
- 👥 **Member Registration:** Manage member profiles and joining records.
- 🧑‍💼 **Librarian Records:** Store and track librarian details.
- 🔁 **Book Loans:** Issue and return books with due date tracking.
- 🔗 **Many-to-Many Relationships:** Handled via `Book_Author` table.
- 🎯 **Database Normalization:** Up to **Third Normal Form (3NF)**.

---

## 🧠 Database Design

### 🧾 ER Diagram

**Entities and Relationships**  
- **Author** — *writes* → **Book**  
- **Book** — *published by* → **Publisher**  
- **Member** — *borrows (via Loan)* → **Book**  
- **Loan** — *managed by* → **Librarian**

---

### 🗃️ Relational Schema (3NF)

| Table         | Attributes                                                                 | Primary Key    | Foreign Keys                                                   |
|---------------|----------------------------------------------------------------------------|----------------|-----------------------------------------------------------------|
| **Author**     | AuthorID, Name, Nationality                                                | AuthorID       | —                                                               |
| **Book**       | ISBN, Title, PublisherID, PublishedYear, Genre, Availability              | ISBN           | PublisherID → Publisher(PublisherID)                           |
| **Publisher**  | PublisherID, Name, Address, Contact                                       | PublisherID    | —                                                               |
| **Member**     | MemberID, Name, Email, Phone, JoinDate                                    | MemberID       | —                                                               |
| **Librarian**  | LibrarianID, Name, Email                                                  | LibrarianID    | —                                                               |
| **Loan**       | LoanID, MemberID, ISBN, LibrarianID, IssueDate, DueDate, ReturnDate       | LoanID         | MemberID → Member(MemberID), ISBN → Book(ISBN), LibrarianID → Librarian(LibrarianID) |
| **Book_Author**| ISBN, AuthorID                                                            | ISBN, AuthorID | ISBN → Book(ISBN), AuthorID → Author(AuthorID)                 |

---

## 🧮 Normalization Summary

- **1NF (First Normal Form):**  
  All tables ensure atomic values and unique entries.  
  ➤ *Example:* `Book_Author` resolves the many-to-many relationship between books and authors.

- **2NF (Second Normal Form):**  
  All partial dependencies are removed by using surrogate keys like `LoanID`.

- **3NF (Third Normal Form):**  
  All transitive dependencies are eliminated to reduce redundancy.  
  ➤ *Example:* `Publisher` table includes only publisher-specific attributes.

---

## 🛠️ Project Files

### 📂 Documentation
- `key milestone 2.docx.pdf.docx` – Includes ER diagram, relational schema, and normalization details.
- `milestone2.docx` – Duplicate support document.

### 📂 Source Code (ZIP)
- Contains backend and/or frontend components for the Library Management System.
- Application logic integrates with the normalized database schema.
- Expected stack: likely web-based interface (HTML/CSS/PHP/Python) + SQL backend.

---

##  Getting Started:

1. **Database Setup**  
   Import the relational schema into MySQL/PostgreSQL.

2. **Configure Application**  
   Update database credentials in the configuration file.

3. **Run the App**  
   Launch the backend server and access the UI in your browser.

---

## 👨‍💻 DONE BY

- **Afaq Amjad, UMAR Iqbal, Ihasan Ullah**
- **Group Members:** Roll Numbers `2135`, `2122`, `2141`  
- **Affiliation:** Academic Project

