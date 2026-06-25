# Project 3 – The Data Warehouse

## Code

```sql
CREATE DATABASE internship_db;

USE internship_db;

CREATE TABLE Interns (
    Intern_ID INT PRIMARY KEY AUTO_INCREMENT,
    Name VARCHAR(100) NOT NULL,
    Role VARCHAR(100) NOT NULL,
    Email VARCHAR(100) UNIQUE,
    Joining_Date DATE,
    Stipend DECIMAL(10,2)
);

INSERT INTO Interns
(Name, Role, Email, Joining_Date, Stipend)
VALUES
('Rahul Kumar', 'Cloud Intern', 'rahul@example.com', '2025-06-01', 10000),
('Priya Sharma', 'Data Analyst Intern', 'priya@example.com', '2025-06-05', 12000),
('Amit Das', 'Developer Intern', 'amit@example.com', '2025-06-10', 15000);

SELECT * FROM Interns;

SELECT Name, Role, Stipend
FROM Interns
WHERE Stipend > 11000;

UPDATE Interns
SET Stipend = 13000
WHERE Name = 'Priya Sharma';

SELECT * FROM Interns;

DELETE FROM Interns
WHERE Intern_ID = 3;

SELECT * FROM Interns;
```

## Outcome

* Created a cloud-based database successfully.
* Designed an `Interns` table with multiple attributes.
* Inserted sample intern records into the database.
* Retrieved records using `SELECT` queries.
* Updated existing data using `UPDATE` statements.
* Deleted records using `DELETE` statements.
* Demonstrated complete CRUD (Create, Read, Update, Delete) operations.
* Improved data organization, management, and storage efficiency.
# Project 4 – The Serverless Logic

## Code

```python
def lambda_handler(event, context):

    num1 = event.get('num1', 0)
    num2 = event.get('num2', 0)

    addition = num1 + num2
    subtraction = num1 - num2
    multiplication = num1 * num2

    if num2 != 0:
        division = num1 / num2
    else:
        division = "Cannot divide by zero"

    result = {
        "Number1": num1,
        "Number2": num2,
        "Addition": addition,
        "Subtraction": subtraction,
        "Multiplication": multiplication,
        "Division": division
    }

    return {
        "statusCode": 200,
        "message": "Calculation completed successfully",
        "result": result
    }
```

## Outcome

* Developed a serverless AWS Lambda function.
* Performed addition, subtraction, multiplication, and division.
* Handled division-by-zero errors safely.
* Returned results in a structured JSON format.
* Demonstrated event-driven cloud computing.
