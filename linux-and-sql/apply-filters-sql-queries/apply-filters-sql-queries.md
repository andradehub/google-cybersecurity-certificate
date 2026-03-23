# Apply Filters to SQL Queries

## Project Description
As a security professional, part of my responsibilities  
include investigating potential security incidents by  
analyzing login attempts and employee data. In this  
project, I used SQL filters to query the organization  
database, identifying suspicious login activity and  
retrieving specific employee information to support  
security updates across the organization.  

---

## Retrieve After Hours Failed Login Attempts  

To investigate a potential security incident that  
occurred after business hours, I queried the  
log_in_attempts table to identify all failed login   
attempts after 18:00.  
```sql
SELECT *
FROM log_in_attempts
WHERE login_time > '18:00'
AND success = 0;
```

**How it works:**
- `WHERE login_time > '18:00'` filters all login  
  attempts that occurred after 6:00 PM  
- `AND success = 0` filters only failed attempts  
- `AND` operator ensures both conditions must be  
  true simultaneously  

---

## Retrieve Login Attempts on Specific Dates

To investigate a suspicious event that occurred on  
2022-05-09, I queried all login attempts on that  
day and the day before.  
```sql
SELECT *
FROM log_in_attempts
WHERE login_date = '2022-05-09'
OR login_date = '2022-05-08';
```

**How it works:**
- `WHERE login_date = '2022-05-09'` filters attempts  
  on the day of the suspicious event  
- `OR login_date = '2022-05-08'` includes the  
  previous day  
- `OR` operator returns results where either  
  condition is true  

---

## Retrieve Login Attempts Outside of Mexico

After determining that suspicious activity did not  
originate from Mexico, I queried all login attempts  
that occurred outside of Mexico.  
```sql
SELECT *
FROM log_in_attempts
WHERE NOT country LIKE 'MEX%';
```

**How it works:**
- `NOT` excludes results that match the condition  
- `LIKE 'MEX%'` matches both MEX and MEXICO values  
  since `%` represents any number of characters  
- This ensures all login attempts from Mexico  
  are excluded regardless of how the country  
  name is stored  

---

## Retrieve Employees in Marketing

To perform security updates on employee machines  
in the Marketing department located in the East  
building, I queried the employees table.  
```sql
SELECT *
FROM employees
WHERE department = 'Marketing'
AND office LIKE 'East%';
```

**How it works:**
- `WHERE department = 'Marketing'` filters only  
  Marketing department employees  
- `AND office LIKE 'East%'` filters employees  
  located in any East building office  
- `%` matches any characters after "East",  
  covering offices like East-170, East-320, etc.  

---

## Retrieve Employees in Finance or Sales 

To perform security updates on machines for  
employees in the Sales and Finance departments,  
I queried the employees table.  
```sql
SELECT *
FROM employees
WHERE department = 'Finance'
OR department = 'Sales';
```

**How it works:**
- `WHERE department = 'Finance'` filters Finance  
  department employees  
- `OR department = 'Sales'` also includes Sales  
  department employees  
- `OR` operator returns employees from either  
  department  

---

## Retrieve All Employees Not in IT

To identify all employees who still need a security  
update, excluding those in the Information  
Technology department, I queried the employees  
table.  
```sql
SELECT *
FROM employees
WHERE NOT department = 'Information Technology';
```

**How it works:**
- `NOT` excludes all employees that match  
  the condition
- `department = 'Information Technology'` targets  
  the IT department specifically  
- This returns all employees in every other  
  department who still need the update  

---

## Summary
In this project, I used SQL filters to investigate  
suspicious login activity and retrieve targeted  
employee data to support security operations. I  
applied AND, OR, and NOT operators to filter across  
multiple conditions, used LIKE with % to match  
patterns in country and office columns, and filtered  
by date and time to identify specific security  
events. These queries demonstrate how SQL can be  
used effectively to support cybersecurity  
investigations and system maintenance tasks.  
