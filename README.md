# SQL DDL Commands – Table Creation and Modification

## 📌 Description
This lab focuses on SQL Data Definition Language (DDL) commands used to create, modify, rename, and delete database tables and columns.

I performed practical SQL tasks on the `students` table, including adding a new column, removing a column, renaming columns and tables, changing data types, inserting a new row, updating existing records, truncating a table, and dropping a table.

## 🎯 Objectives
- Understand SQL DDL commands.
- Create and modify database tables.
- Add and remove columns.
- Rename columns and tables.
- Change column data types.
- Understand the difference between `TRUNCATE` and `DROP`.
- Practise SQL commands using a sample student database.

## 🛠️ Tools Used
- MySQL
- SQL Editor

## 📋 Tasks Performed

### Setup: Create the Students Table

Created a `students` table with the following columns:
- `student_id` – INT, Primary Key
- `student_name` – VARCHAR(50)
- `city` – VARCHAR(30)
- `course` – VARCHAR(40)
- `marks` – INT

```sql
CREATE TABLE students (
    student_id INT PRIMARY KEY,
    student_name VARCHAR(50),
    city VARCHAR(30),
    course VARCHAR(40),
    marks INT
);
```

Inserted the initial five student records.

```sql
INSERT INTO students
    (student_id, student_name, city, course, marks)
VALUES
    (101, 'Asha', 'Pune', 'Data Analytics', 78),
    (102, 'Ravi', 'Mumbai', 'Data Science', 35),
    (103, 'Meena', 'Chennai', 'Data Analytics', 88),
    (104, 'Karan', 'Delhi', 'Excel', 29),
    (105, 'Sara', 'Pune', 'Data Science', 91);
```

### Task 1: Add a New Column

**Requirement:** Add an `email` column to the `students` table.

```sql
ALTER TABLE students
ADD COLUMN email VARCHAR(50);
```

**Outcome:** Added the `email` column to store students' email addresses. Existing records have `NULL` values in this column unless a default value is specified.

### Task 2: Remove a Column

**Requirement:** Remove the `city` column.

```sql
ALTER TABLE students
DROP COLUMN city;
```

**Outcome:** Removed the `city` column and its associated data from the table.

### Task 3: Rename a Column

**Requirement:** Rename `marks` to `score`.

```sql
ALTER TABLE students
RENAME COLUMN marks TO score;
```

**Outcome:** Changed the column name from `marks` to `score` without deleting the existing values.

### Task 4: Change the Data Type

**Requirement:** Change the data type of `marks` from `INT` to `DECIMAL(5,2)`.

```sql
ALTER TABLE students
MODIFY COLUMN marks DECIMAL(5,2);
```

**Outcome:** Changed the data type to support decimal values, such as `78.50`.

**Note:** Perform this task before renaming `marks` to `score`, or modify `score` instead if the column has already been renamed.

### Task 5: Rename the Table

**Requirement:** Rename the `students` table to `learners`.

```sql
RENAME TABLE students TO learners;
```

**Outcome:** Changed the table name from `students` to `learners`, retaining the table's existing structure and records.

### Task 6: Insert a New Row

**Requirement:** Insert student 106 into the `students` table.

```sql
INSERT INTO students
    (student_id, student_name, city, course, marks)
VALUES
    (106, 'Vikram', 'Nagpur', 'Excel', 67);
```

**Outcome:** Inserted a new student record with ID 106.

### Task 7: Update a Student's City

**Requirement:** Change the city of student 103 from Chennai to Hyderabad.

```sql
UPDATE students
SET city = 'Hyderabad'
WHERE student_id = 103;
```

**Outcome:** Updated the city for student 103 without changing other student records.

### Task 8: Verify the Records

Used the `SELECT` command to display the table records and verify the changes.

```sql
SELECT * FROM students;
```

**Outcome:** Displayed the records currently stored in the table.

### Task 9: Truncate the Table

**Requirement:** Remove all rows while keeping the table structure.

```sql
TRUNCATE TABLE students;
```

**Outcome:** Removed all records from the table while retaining its columns and structure.

### Task 10: Drop the Table

**Requirement:** Remove the entire `students` table, including its structure and data.

```sql
DROP TABLE students;
```

**Outcome:** Deleted the table from the database. The table no longer exists.

## 📚 Key Learnings
- Used `CREATE TABLE` to create a database table.
- Used `ALTER TABLE` to add, remove, rename, and modify columns.
- Used `RENAME TABLE` to rename a table.
- Used `INSERT` to add new records.
- Used `UPDATE` with `WHERE` to modify a specific record.
- Used `SELECT` to verify table data.
- Understood `TRUNCATE` and `DROP` and their effects on database tables.

## 📝 Conclusion
This lab provided hands-on experience with SQL table creation, table modification, and data manipulation. I practised DDL commands for changing table structures and also used DML commands to insert and update records.

These tasks helped me understand how SQL manages both database structure and stored data.
