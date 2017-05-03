#Some training about SQL

## Important commands


This allow to select a whole database
```SQL
SELECT * FROM celebs;
```

Or selecting a column:
```SQL
SELECT name FROM celebs;
```

Create a table
```SQL
CREATE TABLE table_name(id INTEGER, name TEXT, age INTEGER);
```

Add element / rows in table
```SQL
INSERT INTO celebs (id, name, age) VALUES (1, 'Justin Bieber', 21);
```


Change / Upadate elements in a column
```SQL
UPDATE celebs 
SET age = 22 
WHERE id = 1; 
```

ADD a column
```SQL
ALTER TABLE celebs ADD COLUMN twitter_handle TEXT; 
```


Delete some rows
```SQL
DELETE FROM celebs WHERE twitter_handle IS NULL;
```

Select the unique occurence in a column
```SQL
SELECT  DISTINCT genre FROM movies;
```


Filtering queries
```SQL
SELECT * FROM movies WHERE imdb_rating > 8;
```

Se_en represents a pattern with a wildcard character. The _ means you can substitute any individual character here without breaking the pattern. The names Seven and Se7en both match this pattern.
```SQL
SELECT * FROM movies
WHERE name LIKE 'Se_en';
```

% is a wildcard character that matches zero or more missing letters in the pattern.
* A% matches all movies with names that begin with "A"
* %a matches all movies that end with "a"

```SQL
SELECT * FROM movies
WHERE name LIKE 'a%';
```

You can use % both before and after a pattern. Here, any movie that contains the word "man" in its name will be returned in the result set. Notice, that LIKE is not case sensitive. "Batman" and "Man Of Steel" both appear in the result set.
```SQL
SELECT * FROM movies
WHERE name LIKE '%man%';
```

The BETWEEN operator is used to filter the result set within a certain range. The values can be numbers, text or dates.
```SQL
SELECT * FROM movies
WHERE name BETWEEN 'A' AND 'J';
```

```SQL
SELECT * FROM movies
WHERE year BETWEEN 1990 AND 2000;
```

AND operator
```SQL
SELECT * FROM movies
WHERE year BETWEEN 1990 AND 2000
AND genre = 'comedy';
```

OR operator
```SQL
SELECT * FROM movies
WHERE genre = 'comedy'
OR year < 1980;
```

Sort data :
```SQL
SELECT * FROM movies
ORDER BY imdb_rating DESC;
```


Sort data and limit number of occurence
```SQL
SELECT * FROM movies
ORDER BY imdb_rating ASC
LIMIT 3;
```




































































