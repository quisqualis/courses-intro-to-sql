# Filtering Rows
###### Filtering: WHERE, =, <>, <, <=, >, >=, AND, OR
- WHERE =
- WHERE <>
- WHERE <=
- WHERE >=
- WHERE = x OR = y  
- WHERE > x AND < y

Get all films released in 2016.
```sql
SELECT *
FROM films
WHERE release_year = 2016;
```

Get the name of the person born on November 11th, 1974.
```sql
SELECT name, birthdate
FROM people
WHERE birthdate = '1974-11-11';
```

Get films released since 2000.
```sql
SELECT title, release_year
FROM films
WHERE release_year > 2000;
FROM films;
```

Get the number of films released since 2000.
```sql
SELECT COUNT(*)
FROM films
WHERE release_year > 2000;
```

Get films released before 2000.
```sql
SELECT title, release_year
FROM films
WHERE release_year < 2000;
```

Get the number of films released before 2000.
```sql
SELECT COUNT(*)
FROM films
WHERE release_year < 2000;
```

Get films released in 1990 or released in 2000.
```sql
SELECT title, release_year
FROM films
WHERE release_year = 1990 OR release_year = 2000;
```

Get films released between 1990 and 2000.
```sql
SELECT title, release_year
FROM films
WHERE release_year >= 1990 AND release_year <= 2000;
FROM films;
```

###### Advanced Filtering: BETWEEN, IN, IS NULL, IS NOT NULL, LIKE, NOT LIKE
- BETWEEN x AND y
- WHERE n IN (x, y, z)
- WHERE x IS NULL
- WHERE x IS NOT NULL
- LIKE
- NOT LIKE

Get films released in the 90s.
```sql
SELECT title, release_year
FROM films
WHERE release_year BETWEEN 1990 AND 2000;
```

Get the number of films released in the 90s.
```sql
SELECT COUNT(*)
FROM films
WHERE release_year BETWEEN 1990 AND 2000;
```

Get films released in 1990 or released in 2000.
```sql
SELECT title, release_year
FROM films
WHERE release_year IN(1990, 2000);
```

Get the number of films released between 2000 and 2015.
```sql
SELECT COUNT(*)
FROM films
WHERE release_year BETWEEN 2000 AND 2015;
```

Get average duration for films released in 1992.
```sql
SELECT AVG(duration)
FROM films
WHERE release_year = 1992;
```

Get average duration for films released in 2012.
```sql
SELECT AVG(duration)
FROM films
AS average_duration
WHERE release_year = 2012;
```

Get the names of people who are still alive.
```sql
SELECT name
FROM people
WHERE deathdate IS NULL;
```

Get the number of films made between 2000 and 2015 with budgets over $100 million.
```sql
SELECT title, budget
FROM films
WHERE release_year
BETWEEN 2000 AND 2015
AND budget > 100000000;
```

Get people whose names begin with 'B'.
```sql
SELECT name
FROM people
WHERE name LIKE 'B%';
```

Get people whose names begin with 'Br'.
```sql
SELECT name
FROM people
WHERE name LIKE 'B%';
```

Get people whose names have 'r' as the second letter.
```sql
SELECT name
FROM people
WHERE name LIKE '_r%';
```

'Get people whose names don't start with A.
```sql
SELECT name
FROM people
WHERE name NOT LIKE 'A%';
```

###### Subqueries
- Subqueries in one table
- Subqueries in two tables