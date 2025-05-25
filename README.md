# PostgreSQL Basics Questions

---

### 1. What is PostgreSQL?

PostgreSQL is a powerful, open-source object-relational database system. It helps store, manage, and retrieve data efficiently. It supports advanced features like transactions, indexing, and complex queries.

---

### 2. What is the purpose of a database schema in PostgreSQL?

A schema in PostgreSQL is like a folder that organizes database objects such as tables, views, and functions. It helps keep the database clean and separates different parts of the application.

Example:

* `public` is the default schema.
* We can create custom schemas like `sales`, `hr`, or `products` to group related tables.

---

### 3. Explain the Primary Key and Foreign Key concepts in PostgreSQL.

* **Primary Key**: A column (or set of columns) that uniquely identifies each row in a table. It must be unique and cannot be null.

Example:

```sql
CREATE TABLE students (
  id SERIAL PRIMARY KEY,
  name VARCHAR(100)
);
```

* **Foreign Key**: A column that creates a link between two tables. It references the primary key in another table.

Example:

```sql
CREATE TABLE enrollments (
  id SERIAL PRIMARY KEY,
  student_id INTEGER REFERENCES students(id)
);
```

---

### 4. What is the difference between the VARCHAR and CHAR data types?

* `VARCHAR(n)`: Stores variable-length strings. We can store any length up to `n` characters. It saves space.
* `CHAR(n)`: Stores fixed-length strings. If the value is shorter, it adds spaces to fill the length.

Use `VARCHAR` when the length of text varies, and use `CHAR` when the length is always the same.

---

### 5. Explain the purpose of the WHERE clause in a SELECT statement.

The `WHERE` clause is used to filter rows in a table. It shows only the rows that meet the given condition.

Example:

```sql
SELECT * FROM students WHERE name = 'Jaber';
```

This query selects only the students whose name is 'Jaber'.

---

### 6. What are the LIMIT and OFFSET clauses used for?

* `LIMIT`: Sets the maximum number of rows to return.
* `OFFSET`: Skips a number of rows before starting to return data.

These are useful for pagination.

Example:

```sql
SELECT * FROM students LIMIT 5 OFFSET 10;
```

This query skips the first 10 rows and returns the next 5 rows.

---

### 7. How can you modify data using UPDATE statements?

The `UPDATE` statement is used to change existing records in a table.

Example:

```sql
UPDATE students
SET name = 'Riyan'
WHERE id = 1;
```

This query changes the name of the student with ID 1 to 'Riyan'.

