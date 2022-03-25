# SQL-Cheat-sheet-Oracle-database
A list of common SQL commands and queries while using Oracle database

# Basics
1. [Querying data](#querying-data )
2. [Sorting data](#sorting-data)
3. [Filtering data](#filtering-data)
4. [Indexing Columns]()
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
