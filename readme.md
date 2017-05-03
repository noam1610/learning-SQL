#Some training about SQL

This is taken from learn SQL in codeAcademy

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


### Calcul Operation on the command



Count the number of rows
```SQL
SELECT COUNT(*) FROM fake_apps;
```

Count a number of rows with filter
```SQL
SELECT COUNT(*) FROM fake_apps
WHERE price = 0;
```


Count the number of rows for each type of price
```SQL
SELECT price, COUNT(*) FROM fake_apps
GROUP BY price;
```
GROUP BY is a clause in SQL that is only used with aggregate functions. It is used in collaboration with the SELECT statement to arrange identical data into groups.

Count the number of rows for each type of price and filtering
```SQL
ELECT price, COUNT(*) FROM fake_apps
WHERE downloads > 20000
GROUP BY price;
```

Make sum over one attribute
```SQL
SELECT SUM(downloads) FROM fake_apps;
```


Find the max value of a parameter over one column
```SQL
SELECT MAX(downloads) FROM fake_apps;
```

filter
```SQL
SELECT name, category, MAX(downloads) FROM fake_apps
GROUP BY category;
```


idem with MIN
```SQL
SELECT MIN(downloads) FROM fake_apps;
```

Select the min value of download for each category label
```SQL
SELECT name, category, MIN(downloads) FROM fake_apps
GROUP BY category;
```

Idem with Average
```SQL
SELECT price, AVG(downloads) FROM fake_apps
GROUP BY price;
```

Round function:
```SQL
SELECT price, ROUND(AVG(downloads), 0) FROM fake_apps
GROUP BY price;
```


###Working with several tables

Let's work with two tables:
 * artists

| artiste   |
| ------------- | -------------   |
|id|     INTEGER     |
|name|      TEXT |



Joining two tables with a foreign key
```SQL
SELECT albums.name, albums.year, artists.name FROM albums, artists
```





