# SQL DML Commands – Insert, Update, and Delete

## 📌 Description

This lab focuses on **Data Manipulation Language (DML)** commands in SQL, which are used to insert new records, update existing records, and delete specific records from database tables.

In this practical task, I worked with a student database using the `students` table. I practised inserting a new student record, updating a student's city, deleting records based on marks, and handling `NULL` values in the email column. I also used the `SELECT` statement to verify the changes made to the table.

## 🎯 Objectives

- Understand the purpose and usage of SQL DML commands.
- Insert new records into a database table using `INSERT`.
- Modify existing records using `UPDATE`.
- Delete specific records using `DELETE`.
- Handle missing or unavailable values using `NULL`.
- Apply conditions using the `WHERE` clause.
- Retrieve and verify records after performing data manipulation operations.

## 🛠️ Tools Used

- **Database:** MySQL
- **Language:** SQL
- **Commands Practised:** INSERT, UPDATE, DELETE, SELECT

## 📚 Tasks Performed

### 1. INSERT Command – Adding a New Record

**Task:** Insert a new student record with student ID 106.

```sql
INSERT INTO students
    (student_id, student_name, city, course, marks)
VALUES
    (106, 'Vikram', 'Nagpur', 'Excel', 67);
```

**Explanation:**
- `INSERT INTO` specifies the table where the record will be added.
- The column names identify the fields in which the values will be stored.
- `VALUES` specifies the data for the new student.

**Outcome:** Added a new record for student 106, with the name Vikram, city Nagpur, course Excel, and marks 67.

### 2. Handling NULL Values

**Task:** Insert a student record with no email address.

```sql
INSERT INTO students
    (student_id, student_name, city, course, marks, email)
VALUES
    (107, 'Priya', 'Pune', 'Data Science', 82, NULL);
```

**Explanation:**
- `NULL` represents a missing, unknown, or unavailable value.
- It is different from an empty string (`''`) or the text `'NULL'`.
- The email column must allow `NULL` values for this query to work.

**Outcome:** Inserted a student record without an email address.

### 3. UPDATE Command – Modifying Existing Data

**Task:** Update the city of student 103 from Chennai to Hyderabad.

```sql
UPDATE students
SET city = 'Hyderabad'
WHERE student_id = 103;
```

**Explanation:**
- `UPDATE students` specifies the table to modify.
- `SET city = 'Hyderabad'` assigns the new city.
- `WHERE student_id = 103` ensures that only the record for student 103 is updated.

**Outcome:** Changed student 103's city from Chennai to Hyderabad without modifying other student records.

### 4. DELETE Command – Removing Records Based on a Condition

**Task:** Delete all student records where marks are below 40.

```sql
DELETE FROM students
WHERE marks < 40;
```

**Explanation:**
- `DELETE FROM students` specifies the table from which records will be removed.
- `WHERE marks < 40` identifies records with marks below 40.
- Only records satisfying the condition are deleted.

**Outcome:** Removed records for students who scored below 40, such as Ravi with 35 marks and Karan with 29 marks, provided those records were still present.

**Important:** Always verify the condition before executing a `DELETE` statement. Without a `WHERE` clause, all records in the table may be deleted.

### 5. SELECT Command – Verifying the Changes

**Task:** Display all student records after performing the DML operations.

```sql
SELECT * FROM students;
```

**Explanation:**
- `SELECT` retrieves data from a database table.
- `*` selects all columns.
- The query helps verify inserted records and updated values and check which records remain after deletion.

**Outcome:** Retrieved the current student records to verify the results of the data manipulation operations.

## 📖 Key Learnings

- Learned to insert single or multiple records into a table.
- Practised inserting `NULL` values into a column.
- Updated existing records using the `UPDATE` command.
- Used the `WHERE` clause to target specific records.
- Deleted records based on a condition using `DELETE`.
- Verified data changes using `SELECT`.
- Understood the importance of checking conditions before updating or deleting records.

## ✅ Conclusion

This lab provided hands-on experience with SQL DML commands for managing records in a relational database. I practised inserting new student details, handling missing email values, updating city information, deleting records based on marks, and verifying the resulting data.

These operations are essential for maintaining accurate and consistent data in database applications.
