# SQL

> Structured English QUEry Language

## Create Table and Values

```sql
CREATE TABLE groceries (id INTEGER PRIMARY KEY NOT NULL,
name VARCHAR(255),
quantity INTEGER);
```

```sql
INSERT INTO groceries VALUES (1, "Bananas", 4);
```

## Queries

At the most basic:
```sql
SELECT *
FROM <table1>
```

`*` is wild card, signifies "all". Can replace with `<field1>, <field2>` etc.

### Aggregators

`COUNT(*)` --> gives the number of entries
\
`SUM(population)` --> gives total population for all items
\
`AVG(population)` --> average
\
`DISTINCT name` --> gives only the distinct names
\
`LIMIT 1` --> only shows the desired number of rows
\
`ROUND(29.3579, 2)` --> 29.36
\
`LENGTH('Hello')` --> 5
\
`LEFT('Hello', 1)` --> H
\
`SELECT surname || ', ' || firstname` --> outputs: Surname, Firstname
\ 
`NOW()` --> gives the current timestamp (based on server timezone)


### Comparisons

`AND, OR, XOR, <>`
\
`LIKE (%cat%)` --> finds all values with 'cat' in it
\
`[NOT] IN ('carrot', 'pickle')` --> find all values that have carrot or pickle (or NOT)
\ 
`BETWEEN 1960 AND 1970` --> find all values within the specified range

### GROUP BY and HAVING

> `GROUP BY`: The `WHERE` clause is processed (on individual lines), then the `GROUP BY` is applied

```sql
SELECT continent
FROM world
WHERE population > 100000000
GROUP BY continent
```

> `HAVING`: List continents that have a population of at least 100000000 (after `GROUP BY`)

```sql
SELECT continent
FROM world
GROUP BY continent
HAVING population > 100000000
```

## JOIN

```sql
SELECT * FROM table1
JOIN table2 ON table1.id = table2.other_id
```

The id's for each table must allow the tables to connect (Primary Key to Foreign Key)

### Sub Queries

```sql
SELECT * FROM exercise_logs
WHERE type IN (SELECT type FROM drs_favorites);
```
--> Results from tbe subquery are used in the main query. The can be a single results (i.e. SUM), or a separate table.

## CASE

```sql
SELECT type, heart_rate,
  CASE
    WHEN heart_rate > (220 - 30) THEN 'above max'
    WHEN heart_rate > ROUND(0.9 * (220 - 30)) THEN 'above target'
    WHEN heart_rate > ROUND(0.5 * (220 - 20)) THEN 'within target'
    ELSE 'below target'
  END AS 'hr_zone'
FROM exercise_logs
```

The `CASE` statement creates a new column (by the name `hr_zone`), and assigns each value based on the `WHEN` statements.


## ALL

```sql
SELECT name
FROM world
WHERE gdp > ALL (SELECT gdp
                FROM world
                WHERE gdp > 0
                AND continent = 'Europe');
```
--> selects all countries that have a gdp greater than all of the countries of Europe

## Correlated Sub Queries

A correlated sub-query works like a nested loop: the sub-query only has access to rows related to a single record at a time in the outer query.

One way to interpret the line in the `WHERE` clause that references two tables is "where the correlated values are the same".

```sql
SELECT continent, area, name
FROM world x
WHERE area >= ALL (SELECT area
                  FROM world y
                  WHERE y.continent = x.continent
                  AND area > 0);
```
--> "Select the country details from world where the area is greater than or equal to the area of all countries where the continent is the same"


## EXPLAIN

Shows the execution plan for the supplied statement, and <strong>the estimated statement execution cost</strong> (i.e. how long it will take to run the statement).


```sql
EXPLAIN SELECT * FROM foo;
```

results in:

```sql
          QUERY PLAN
  ---------------------------
  Seq Scan on foo (cost=0.00..155.00 rows=10000 width=4)
```

