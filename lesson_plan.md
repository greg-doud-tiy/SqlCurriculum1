## Lesson Plan

### Duration

20 minutes

### Instructor Preparation

Refresh your knowledge of the SELECT statement syntax including the WHERE clause and the ORDER BY clause including the ASC and DESC parameters.

Gather your thoughts about a table you can describe to the students that they can create SELECT statements to report on the data withing the table. Suggestions include EMPLOYEE, CUSTOMER, STUDENT, ORDER, and PRODUCT

### Lesson

In this lesson, students will learn how to use the SQL SELECT statement to retrieve data from a table, showing only the columns they want, limiting the result to only rows that meet certain criteria, and sorting the result.

It is suggested that the instructor not discuss GROUP BY and HAVING clauses until the stuents have a good understanding of the SELECT results.

#### Open / Pre-lesson Activity

Talk about the data in SQL tables like employees and how there can be many rows in this table about all employees. Sometimes, reports need the information on all employes, but most of the time, only certain information on certain employees are needed for the report and the data must be sorted differently than how it is stored in the table. While this work can be done many ways, usually the most efficient way is to create a SELECT statement and let the SQL database produce only the data requested and sorted in the proper sequence

#### Lecture

When data from a SQL table is needed, there are a number of ways to get it. It could be pulled into a spreadsheet or processed within a program, but the most efficient way is to let the SQL database retrieve that data. This is done using a SELECT statment.

With a single SELECT statment, you can retrieve only the columns you want and only the rows that match some criteria. Then the results can be sorted for you. All this from a single SELECT statment. Here is the syntax of a SELECT statement

```sql
SELECT [columnList | *] FROM [tablename] WHERE [whereCondition] ORDER BY [columnList]
```

The keyword _SELECT_ is required and must always be the first item in the statement. Since SQL is NOT case sensitve, it can be spelled with or without the capital letters so it can be SELECT or Select or select.

After SELECT, the columns to be returned are listed each separated by a comma. An asterisk (*) is a shortcut meaning all the columns in the table in the order they were defined. When listing the columns to be returned, they can be listed in any order.

The FROM clause with tablename is required.

The optional WHERE clause is to limit the number of rows returned based on the whereCondition. The whereCondition is in the form of columnName comparator value. Multiple where conditions can include the logical AND, OR, NOT. Parentheses can be used to change the order of evaluation. If the WHERE clause exists, it must come right after the FROM clause.

The optional ORDER BY clause is used to sort the result based on the columnList where each item in the columnList is a columnName separated by a comma. The sort defaults to ascending on each column unless the the DESC parameter is specified after the columnName which causes the sort to be descending. The ORDER BY clause must follow the columnList and WHERE clause if it exists.

If there was an Employee table that had the columns: Name, Address, City, State, Zip and we wanted to produce a report that included the Name and State of all employees from the states of Ohio, Indiana, or Kentucky ordered by State then Name, we could use this SELECT statement.

```sql
SELECT Name, State FROM Employee WHERE State = 'OH' OR State = 'IN' OR State = 'KY' ORDER BY State, Name
```

This would produce a result like this:

| Name | State |
| ---- | ----- |
| Cathy Craft | IN |
| Fran Franklin | IN |
| Bruce Bowen | KY |
| Dave Dowers | KY |
| Ed Evans | OH |
| Alice Albright | OH | 

While there are programmatic ways to produce this same result, it is almost always better to let SQL do it.

#### Close / Post-lesson Activity

Ask the students to assume the employee table used in the lession. How would they produce a report from SQL that listed the cities and employee names (in that order) from the cities of Greenville, Tampa, and Minneapolis. Sort the result in descending city sequence.
