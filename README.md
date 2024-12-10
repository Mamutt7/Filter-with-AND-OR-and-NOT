# Filter-with-AND-OR-and-NOT

## Activity overview
As a security analyst, you’ll likely need to analyze data. And often finding the specific data you’ll need depends on more than one factor.

To retrieve specific pieces of information from the database, you can filter for multiple conditions. You can also filter for what does not match a particular condition.

In this lab activity, you’ll use the AND, OR, and NOT operators to create more complex filters for SQL queries.

## Scenario
In this scenario, you need to obtain specific information about employees, their machines, and the departments they belong to from the database.

Your team needs data to investigate potential security issues and to update computers.

You are responsible for filtering the required information from the database.

Here’s how you’ll do this task: First, you’ll retrieve all failed login attempts after business hours. Second, you’ll retrieve all login attempts that occurred on specific dates. Third, you’ll retrieve logins that didn't originate in Mexico. Fourth, you’ll retrieve information about certain employees in the Marketing department. Fifth, you’ll retrieve information about employees in the Finance or the Sales department. Finally, you’ll obtain information about employees who are not in the Information Technology department.

### Task 1. Retrieve after hours failed login attempts
Your team is investigating failed login attempts that were made after business hours. You want to retrieve this information from the login activity. You’ll identify all unsuccessful attempts after 18:00.

The login_time column in the log_in_attempts table contains information on when login attempts were made. Office hours end at '18:00'.

The success column in the log_in_attempts table contains values of TRUE or FALSE to indicate whether the login was successful. MySQL stores Boolean values as 1 for TRUE, and 0 for FALSE. This means that TRUE is represented as 1, and FALSE represented as 0 in the success column.

- Use the AND operator to retrieve the failed login attempts that occurred after business hours. Replace the X and Y with the correct values to filter for the records you need:

```
SELECT *
FROM log_in_attempts
WHERE login_time > 'X' AND success = Y;
```
![image](https://github.com/user-attachments/assets/e287a1c3-acdf-4bc4-8057-087813b6c735)


### Task 2. Retrieve login attempts on specific dates
Your team is investigating a suspicious event that occurred on '2022-05-09'. You want to retrieve all login attempts that occurred on this day and the day before ('2022-05-08').

The login_date column in the log_in_attempts table contains information on the dates when login attempts were made.

- Use the OR operator to retrieve the failed login attempts on the specified days. Replace the X and Y with the correct values to filter for the records you need:

```
SELECT * 
FROM log_in_attempts 
WHERE login_date = 'X' OR login_date = 'Y';
```
![image](https://github.com/user-attachments/assets/f5b78d90-859c-4ac5-b12e-a3b013381aca)


### Task 3. Retrieve login attempts outside of Mexico
Now, your team is investigating logins that did not originate in Mexico, and you need to find this information. Note that the country field includes entries with 'MEX' and 'MEXICO'. You should use the NOT and LIKE operators and the matching pattern 'MEX%'.

- Run the following SQL query to retrieve login attempts that did not originate in Mexico. Replace X with the correct operator and Y with the correct pattern to filter for the information you need:

```
SELECT * 
FROM log_in_attempts
WHERE X country LIKE 'Y';
```
![image](https://github.com/user-attachments/assets/b9d9df88-d5c5-41eb-89f5-4b0b4e6782fb)


### Task 4. Retrieve employees in Marketing
For tasks 4, 5 and 6 you need to retrieve the information from the department and office columns in the employees table.

You can run the following SQL query if you need to view the columns and values in the employees table:

```
SELECT * 
FROM employees;
```

Your team is updating employee machines, and you need to obtain the information about employees in the 'Marketing' department who are located in all offices in the East building (such as 'East-170' or 'East-320').

- Write a SQL query to retrieve this information from the employees table. Select all columns and include filters on the department and office columns to return only the needed records.
![image](https://github.com/user-attachments/assets/e9e1950e-5e8f-4dd2-a5b7-46087c0b64a6)

### Task 5. Retrieve employees in Finance or Sales
Now, your team needs to perform a different update to the computers of all employees in the Finance or the Sales department, and you need to locate information on these employees.

- Write a SQL query to retrieve records for employees in the 'Finance' or the 'Sales' department.
![image](https://github.com/user-attachments/assets/d15dedae-4501-480e-8358-d74eef6b8140)


### Task 6. Retrieve all employees not in IT
Your team needs to make one more update. This update was already made to employee computers in the Information Technology department. The team needs information about employees who are not in that department. You should use the NOT operator to identify these employees.

- Write a SQL query to retrieve records for employees who are not in the 'Information Technology' department.
![image](https://github.com/user-attachments/assets/9bf0f0c1-91c5-42e5-9161-7c1b56debfc1)

### Conclusion

You now have practical experience in using SQL to

- run SQL queries to retrieve information from a database and
- apply AND, OR, and NOT operators to filter SQL queries.
