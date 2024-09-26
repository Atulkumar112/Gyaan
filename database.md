# Database Documentation

## Joins
Joins are used to combine rows from two or more tables based on a related column between them.

1. INNER JOIN: Returns records that have matching values in both tables.
```
SELECT employees.name, departments.name
FROM employees
INNER JOIN departments ON employees.department_id = departments.id;
```

2. LEFT JOIN (or LEFT OUTER JOIN): Returns all records from the left table and the matched records from the right table. If there is no match, NULL values are returned for columns from the right table.

``` 
SELECT employees.name, departments.name
FROM employees
LEFT JOIN departments ON employees.department_id = departments.id;
 ```

3. RIGHT JOIN (or RIGHT OUTER JOIN): Definition: Returns all records from the right table and the matched records from the left table. If there is no match, NULL values are returned for columns from the left table.
 ```
SELECT employees.name, departments.name
FROM employees
RIGHT JOIN departments ON employees.department_id = departments.id;
```


4. FULL JOIN (or FULL OUTER JOIN): Returns all records when there is a match in either left or right table records. If there is no match, NULLs are returned for non-matching rows.

 ```
SELECT employees.name, departments.name
FROM employees
FULL JOIN departments ON employees.department_id = departments.id;
```

5. CROSS JOIN: Returns the Cartesian product of the two tables, meaning every row from the first table is combined with every row from the second table.

 ```
SELECT employees.name, departments.name
FROM employees
CROSS JOIN departments;
```

6. SELF JOIN: A join in which a table is joined with itself.

 ```
SELECT a.name AS Employee, b.name AS Manager
FROM employees a
INNER JOIN employees b ON a.manager_id = b.id;
```

NOTE: When you use JOIN without specifying the type (e.g., INNER, LEFT, RIGHT, FULL), SQL assumes you are using an INNER JOIN by default.
