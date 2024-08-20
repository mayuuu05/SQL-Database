# SQL-Database

# 18.1 Employee Management Database

This project demonstrates the creation and management of an `employee` database table using SQL. The operations include inserting employee data, retrieving specific information, updating records, and deleting records.

## Table Structure

The `employee` table is structured as follows:

| Field    | Type    | Description                            |
|----------|---------|----------------------------------------|
| `id`     | INTEGER | Unique identifier for each employee. Primary key with AUTOINCREMENT. |
| `name`   | TEXT    | Name of the employee. Cannot be null.  |
| `role`   | TEXT    | Job role or title of the employee.     |
| `salary` | INTEGER | Salary of the employee. Cannot be null.|
| `age`    | INTEGER | Age of the employee. Cannot be null.   |
| `address`| TEXT    | Residential address of the employee.   |
| `phone`  | INTEGER | Contact number of the employee. Cannot be null. |

## SQL Operations

### 1. Create the `employee` Table

```sql
CREATE TABLE "employee" (
    "id" INTEGER NOT NULL,
    "name" TEXT NOT NULL,
    "role" TEXT,
    "salary" INTEGER NOT NULL,
    "age" INTEGER NOT NULL,
    "address" TEXT,
    "phone" INTEGER NOT NULL,
    PRIMARY KEY("id" AUTOINCREMENT)
);
```
### 2. Insert Employee Data

- Add a new employee with all details:

  ``` sql
  INSERT INTO employee (id, name, role, salary, age, address, phone) VALUES (1, "John Doe", "Manager", 75000, 35, "123 Main St", "555-1234");
  ```

- Add multiple employees with selective data:

  ``` sql
  INSERT INTO employee (name, role, salary, age, address, phone) VALUES 
  ("Eve Carter", "Accountant", 58000, 32, "789 Elm St", "555-1235"),
  ("Frank Wright", "HR", 62000, 36, "321 Birch St", "555-2345"),
  ("Grace Hall", "Developer", 66000, 29, "456 Pine St", "555-3456"),
  ("Henry King", "Manager", 72000, 45, "123 Spruce St", "555-4567"),
  ("Ivy Scott", "Designer", 61000, 27, "789 Maple St", "555-5678"),
  ("Jack Turner", "QA", 54000, 31, "321 Oak St", "555-6789");

  ```

  ### 3. Retrieve Employee Data
  - Retrieve all employee information:

    ``` sql
    SELECT * FROM employee;

    ```
  - Get specific columns for all employees (e.g., name, salary):

    ``` sql
    SELECT name, salary FROM employee;


    ```

  - Find employees with a particular role (e.g., Manager):

    ``` sql
    SELECT * FROM employee WHERE role = "Manager";

    ```

  - Search for employees with names containing "An" (case-insensitive):
    ``` sql
    SELECT * FROM employee WHERE name LIKE "%An%";


    ```

  - Find employees older than 30 and earning more than $70,000:

    ``` sql
    SELECT * FROM employee WHERE age > 30 AND salary > 70000;


    ```


### 4. Update Employee Records

- Change the salary of an employee with ID 100:
    ```sql
    UPDATE employee SET salary = 50000 WHERE id = 100;

    ```
- Update the address for employees in the 'Sales' role:
    ```sql
    UPDATE employee SET address = "456 Market St" WHERE role = "Sales";

    ```


### 5. Delete Employee Records
    
- Remove an employee with ID 101:
    ```sql
    DELETE FROM employee WHERE id = 101;

    ```



- Delete all employees under 20 (assuming it's not a valid age):
    ```
    DELETE FROM employee WHERE age < 20;

    ```

