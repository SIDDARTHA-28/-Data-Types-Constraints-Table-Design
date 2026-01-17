# -Data-Types-Constraints-Table-Design
Intern learns proper schema design and validation rules
CREATE TABLE students (
    student_id INT PRIMARY KEY,
    first_name VARCHAR(50) NOT NULL,
    last_name VARCHAR(50) NOT NULL,
    email VARCHAR(100) UNIQUE,
    birth_date DATE
);
INSERT INTO students (student_id, first_name, last_name, email, birth_date)
VALUES 
    (1, 'John', 'Doe', 'john@example.com', '2000-01-01'),
    (2, 'Jane', 'Smith', 'jane@example.com', '1999-05-15');
    student_id,first_name,last_name,email,birth_date
1,John,Doe,john@example.com,2000-01-01
2,Jane,Smith,jane@example.com,1999-05-15
INSERT INTO students (student_id, first_name, last_name, email, birth_date)
VALUES (3, NULL, 'Test', 'test@example.com', '2001-02-02');
INSERT INTO students (student_id, first_name, last_name, email, birth_date)
VALUES (3, 'Test', 'User', 'john@example.com', '2001-02-02');
INSERT INTO students (student_id, first_name, last_name, email, birth_date)
VALUES (1, 'Duplicate', 'ID', 'dup@example.com', '2002-03-03');
ALTER TABLE students ADD COLUMN gpa DECIMAL(3,2);
UPDATE students SET gpa = 3.5 WHERE student_id = 1;
UPDATE students SET gpa = 4.0 WHERE student_id = 2;
ALTER TABLE students CHANGE birth_date dob DATE;
ALTER TABLE students DROP COLUMN gpa;
-- Create table with constraints
CREATE TABLE students (
    student_id INT PRIMARY KEY,
    first_name VARCHAR(50) NOT NULL,
    last_name VARCHAR(50) NOT NULL,
    email VARCHAR(100) UNIQUE,
    birth_date DATE
);

-- Insert valid data
INSERT INTO students (student_id, first_name, last_name, email, birth_date)
VALUES 
    (1, 'John', 'Doe', 'john@example.com', '2000-01-01'),
    (2, 'Jane', 'Smith', 'jane@example.com', '1999-05-15');

-- Add new column
ALTER TABLE students ADD COLUMN gpa DECIMAL(3,2);

-- Update data
UPDATE students SET gpa = 3.5 WHERE student_id = 1;
UPDATE students SET gpa = 4.0 WHERE student_id = 2;

-- Rename column
ALTER TABLE students CHANGE birth_date dob DATE;

-- Drop column
ALTER TABLE students DROP COLUMN gpa;
