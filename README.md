# DBMS_Project
A relational database-backed system designed to streamline and manage core library operations including book lending, author tracking, librarian administration, and publisher management. This academic project demonstrates database design using ER modeling, normalization (1NF to 3NF), and schema conversion to support scalable, consistent data handling.

---

## 📁 Project Structure

Library-Management-System/
├── ER Diagram & Conceptual Schema
├── Database Normalization (1NF, 2NF, 3NF)
├── Relational Schema Tables
├── Application Source Code (Frontend & Backend)
├── Documentation/
│ ├── key milestone 2.docx.pdf.docx
│ └── milestone2.docx
└── README.md

yaml
Copy
Edit

---

## 🧩 Features

- 📘 Manage a catalog of Books with Author relationships
- 🧑‍🏫 Register and track Librarians
- 👥 Manage Library Members
- 📦 Link Books with Publishers
- 🔁 Handle Book Borrowing and Loan Transactions
- ✅ Fully normalized database schema in 3NF
- 🔗 Supports many-to-many relationship (Book ↔ Author)

---

## 🧠 Database Design

### 🗺️ ER Diagram Entities & Relationships

- **Author** → Writes → **Book**
- **Book** → Published By → **Publisher**
- **Member** → Borrows via → **Loan**
- **Loan** → Managed By → **Librarian**

---

### 🧾 Relational Schema (3NF)

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

## 📐 Normalization Process

- **1NF:** All attributes are atomic.  
- **2NF:** Eliminated partial dependencies using surrogate keys (e.g., `LoanID`).  
- **3NF:** Removed transitive dependencies ensuring all non-key attributes depend solely on the primary key.

---

## 🚀 Getting Started

> *Instructions below are placeholders — please update based on your actual application framework (e.g., Flask, PHP, Node.js).*

### Prerequisites

- MySQL / PostgreSQL
- Python / Node.js (depending on implementation)
- Any modern browser for the frontend

### Steps

1. Import the SQL schema into your database server.
2. Configure database credentials in your application's config file.
3. Start the backend server:
   ```bash
   python app.py     # for Flask
   npm run dev       # for Node.js
Open your browser and navigate to http://localhost:3000 or the specified port.

📄 Documentation
The following files include the schema design, normalization steps, and conceptual diagrams:

key milestone 2.docx.pdf.docx

milestone2.docx

🧑‍💻 Authors
Afaq Amjad

Group Members: 2122, 2135, 2141

This project was created as part of an academic coursework milestone.
