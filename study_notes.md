## Study Notes

### Terminology

  - SELECT: A statement in SQL that returns data from tables
  - Sql table: An entity in SQL that stored data about an entity.
  - Sql Database: A collection of tables
  - Spreadsheet: An entity that displays data in rows and columns
  - Column: An piece of data that occurs for every row in a table
  - whereCondition: One or more condition statement meant to specify the rows to be included in the result.
  - columnList: One or more column names separated by a comma
  - FROM tablename: Required clause specifying the table to be accessed


### Examples

```sql
-- Retrieves all columns and all rows from the Employee table
SELECT * FROM Employee

-- Retrieves the Name, Address, and State columns and all rows from the Employee table
SELECT Name, Address, State FROM Employee

-- Retrieves the Name, Address, and State columns for all rows from the Employee table
-- where the State is SC
SELECT Name, Address, State FROM Employee WHERE State = 'SC'

-- Retrieves the Name, Address, and State columns for all rows from the Employee table
-- where the State is SC and order the result by the Name in descending sequence
SELECT Name, Address, State FROM Employee WHERE State = 'SC' ORDER BY Name desc
```