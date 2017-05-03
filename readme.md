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