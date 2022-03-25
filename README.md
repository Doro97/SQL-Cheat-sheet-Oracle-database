# SQL-Cheat-sheet-Oracle-database
A list of common SQL commands and queries while using Oracle database

# Basics
1. [Querying data](#querying-data )
2. [Sorting data](#sorting-data)
3. [Filtering data](#filtering-data)
4. [Joining tables](#joining-tables)
5. [Querying data]()
6. [Adding Columns]()
7. [Querying the Oracle Data dictionary]()
8. [Update Data]()
9. [Aggregate Queries]()
10. [Compressing data]()
11. [Delete data]()
12. [Drop tables]()
13. [Un-dropping tables]()

## Querying Data
To retrieve data from one or more columns of a table:

```
 SELECT column_1, column_2,
 FROM table_name;
```

## Sorting Data
To sort data use:

``` 
SELECT column_1,column_2 
FROM table_name 
ORDER BY column_1 [ASC | DESC] [NULLS FIRST | NULLS LAST],column_2 DESC
 ```

where ```ASC``` is ascending order and ```DESC``` is descending order.

## Filtering Data

1. DISTINCT-eliminates duplicate rows from the output of a query.

    ``` SELECT DISTINCT column_1,column_2 FROM table_name;```

2. WHERE- specify a condition for rows in the result set returned by a query.

    ``` SELECT select_list FROM table_name WHERE search_condition ORDER BY sort_expression;```
3. AND – combine two or more Boolean expressions and return true if all expressions are true.

    ``` expression_1 AND expression_2 ```
4. OR–  combine two or more Boolean expressions and return true if one of the expressions is true.
    ```expression_1 OR expression_2```
5. FETCH –limit rows returned by a query.

    ```
    [ OFFSET offset ROWS]

    FETCH  NEXT [  row_count | percent PERCENT  ] ROWS  [ ONLY | WITH TIES ]
     ```

    * The ```OFFSET``` clause specifies the number of rows to skip before the row limiting starts
    * The ```WITH TIES``` returns additional rows with the same sort key as the last row fetched.When using ```WITH TIES```, an ```ORDER BY``` clause must be used in the query. 


6. IN – determine if a value matches any value in a list or a subquery.
    ```expression [NOT] IN (v1,v2,...)```
    or

    ```expression [NOT] IN (subquery)```
7. BETWEEN – filter data based on a range of values:

    ```expression [ NOT ] BETWEEN low AND high```
8. LIKE  – perform matching based on specific patterns:

    ```expresion [NOT] LIKE pattern [ ESCAPE escape_characters ]``` 
9. IS NULL and IS NOT NULL – check if an expression or values in a column is NULL or not.

    ```expression |  column  IS NULL```

## Joining tables
1. INNER JOIN-to query rows from a table that have matching rows from another table
To query data from two or more related tables, you use the ```INNER JOIN``` clause

```
SELECT *
FROM table1 INNER JOIN table2 
ON join_predicate;
```

Use the ```USING``` clause to specify which columns to test for equality when joining tables.

```
SELECT *
FROM table1 INNER JOIN table2 
USING( column1, column2, ... );
```

2. LEFT JOIN- to select rows from the left table that have or don’t have the matching rows in the right table.

```
SELECT column_list
FROM t1 LEFT JOIN t2 ON
    t1.c1 = t2.c1
    AND t1.c2 = t2.c2
    AND t1.c3 = t2.c3
    AND ... ;
```

3. RIGHT JOIN-to query rows from the right table that have or don’t have the matching rows in the left table.
```
SELECT column_list
FROM T1
RIGHT OUTER JOIN T2 
ON join_predicate;
```

4. FULL OUTER JOIN

```
SELECT select_list
FROM T1 FULL OUTER JOIN T2 
ON join_condition;
```

5. CROSS JOIN-to make a Cartesian product from multiple tables
```
SELECT column_list
FROM T1 
CROSS JOIN T2; 
```

6. SELF-JOIN-a join that joins a table with itself
```
SELECT
    column_list
FROM
    T t1
INNER JOIN T t2 ON
    join_predicate;

```