# MongoDB Fundamentals - Week 1
# MongoDB Queries & Scripts

This project demonstrates basic and advanced MongoDB queries, aggregation pipelines, and indexing operations.  
It also includes sample data for testing.

---

## 📦 Prerequisites
- **MongoDB** installed locally OR a connection to **MongoDB Atlas**
- **MongoDB Shell (`mongosh`)** installed
- (Optional) **MongoDB Compass** for GUI exploration

---

## 🚀 Getting Started

### 1. Clone or Download
Download this project folder and open it in your terminal.

### 2. Start MongoDB
If using **local MongoDB**:
```bash
mongod --dbpath /your/data/path
If using Atlas (cloud):

Open MongoDB Compass

Copy your connection string

Use it in the shell:

bash
Copy code
mongosh "mongodb+srv://<your-cluster>.mongodb.net/<your-db>" --username <your-user>
📂 Files
queries.js → Contains all the queries (basic, advanced, aggregations, indexing).

sampleData.js → Inserts test data into the books collection.

README.md → Documentation (this file).

📝 Running the Scripts
1. Insert Sample Data
Run in shell:

bash
Copy code
mongosh < sampleData.js
This will create the books collection and insert documents.

2. Run Queries
Run:

bash
Copy code
mongosh < queries.js
Alternatively, you can open the shell and paste individual commands from queries.js.

📚 Queries Included
Basic Queries
Find all books in a specific genre

Find books published after a certain year

Find books by a specific author

Update the price of a specific book

Delete a book by its title

Advanced Queries
Find books that are in stock and published after 2010

Use projection to return only title, author, and price

Sort by price (ascending/descending)

Implement pagination (5 books per page)

Aggregation Pipelines
Calculate the average price of books by genre

Find the author with the most books

Group books by decade and count them

Indexing
Create an index on title

Create a compound index on author and published_year

Use explain() to demonstrate query performance with indexes

✅ Example
js
Copy code
// Find programming books published after 2010
db.books.find(
  { genre: "Programming", published_year: { $gt: 2010 } },
  { title: 1, author: 1, price: 1, _id: 0 }
).pretty()

## 📸 Sample Data in MongoDB Compass

Here’s a view of the `books` collection with sample documents:

![Sample data in Compass](screenshots\compass-sample.png)
