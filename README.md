# Subqueries - the cherry on top
Think of a query as a cake. A cake can have multiple layers contained within it and even layers within those layers. Each of these layers are our subqueries, and when you put all of the layers together, you get a cake (query). Usually, you will find subqueries nested in the SELECT, FROM, and/or WHERE clauses. There is no general syntax for subqueries,  but the syntax for a basic subquery is as follows:

    (SELECT [DISTINCT] subquery_select_argument
    FROM {table_name | view_name}
    {table_name | view_name} ...
    [WHERE search_conditions]
    [GROUP BY aggregate_expression [, aggregate_expression] ...]
    [HAVING search_conditions])

There are a few rules that subqueries must follow:

    Subqueries must be enclosed within parentheses

    A subquery can have only one column specified in the SELECT clause. But if you want a subquery to compare multiple columns, those columns must be selected in the main query.

    Subqueries that return more than one row can only be used with multiple value operators, such as the IN operator which allows you to specify multiple values in a WHERE clause.

    A subquery can’t be nested in a SET command. The SET command is used with UPDATE to specify which columns (and values) are to be updated in a table.

The HAVING Clause
    The HAVING clause was added to SQL because the WHERE keyword could not be used with aggregate functions.

    SQL HAVING Syntax
    SELECT column_name, aggregate_function(column_name)
    FROM table_name
    WHERE column_name operator value
    GROUP BY column_name
    HAVING aggregate_function(column_name) operator value;

The SQL CASE Expression
    The CASE expression goes through conditions and returns a value when the first condition is met (like an if-then-else statement). So, once a condition is true, it will stop reading and return the result. If no conditions are true, it returns the value in the ELSE clause.

    If there is no ELSE part and no conditions are true, it returns NULL.

    CASE Syntax
    CASE
        WHEN condition1 THEN result1
        WHEN condition2 THEN result2
        WHEN conditionN THEN resultN
        ELSE result
    END;

The COUNT() function returns the number of rows that matches a specified criteria.

SQL COUNT(column_name) Syntax

The COUNT(column_name) function returns the number of values (NULL values will not be counted) of the specified column:

    SELECT COUNT(column_name) FROM table_name;
    SQL COUNT(*) Syntax
    The COUNT(*) function returns the number of records in a table:

    SELECT COUNT(*) FROM table_name;
    SQL COUNT(DISTINCT column_name) Syntax

The COUNT(DISTINCT column_name) function returns the number of distinct values of the specified column:

    SELECT COUNT(DISTINCT column_name) FROM table_name;