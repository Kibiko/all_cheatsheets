 # SQL Cheatsheet

# Table of Contents

1. [Background](#background)
2. [Starting Up](#starting-up)
3. [Entity Relationship Diagrams](#entity-relationship-diagrams)
4. [Operations](#operations)

## ***Background***

Two types of databases:

- Relational (SQL)
- Non-Relational (NoSQL)

### SQL (Structured Query Language)
* Everything is structured and the rules are set

### NoSQL (Not Only SQL)
- One user may have their data stored differently to others
- For example more parameters or different type
- More flexibility if changes to the rules need to be made
- Usually made with JavaScript due to it's flexibility

### **Dialects**

Most common dialects include,

- MySQL (owned by Microsoft)
- PostgreSQL
- H2
- SQLite

These are different languages but the format of the commands follow the same way in each dialect. We will be using PostgreSQL but this is transferrable to MySQLm similar to learning different coding languages.

### **Process and Database**

![SQL Queries](/images/sql_queries.png)

![Database](/images/database.png)

## ***Starting Up***

Entering the postgresql interface: 
```
psql
```

Creating a database (can be from any directory):
```
kevin=# CREATE DATABASE example; 
```
If you are missing the semi-colon on the end, command does not execute (no prompt) and `kevin=#` changes to `kevin-#`, this indicates it is reading the next line, therefore finish off with semi-colon on next line.

|Command|Description|
|----|-----|
|`\l`|lists all databases|
|DROP DATABASE example|deletes the database named example|
|`\q`|exits postgresql interface|
|createdb [database name]|creates a database from command line|
|which psql|shows directory for all the database records|

## ***Entity Relationship Diagrams***

UML for SQL, snake case for names.

![Movies DB](/images/movies_db.png)

- INT in SQL is the same for *int* in Java, if larger numbers are need then INT8 which is equivalent to *long*.

- VARCHAR(255) allocates 255 bits of memory which equals 255 characters.

- SERIAL is still a numerical type. If we put records in a database, we will not need to put an id as SERIAL does it automatically. If records are removed, the SERIAL will not go back to a previously assigned SERIAL number and will continue automatically increment. SERIAL8 if we need more. Alternatively we can use INT with constraint Unique, but better to do SERIAL.

*cinema.sql*
```sql
DROP TABLE movies; -- this makes sure we drop table if we keep making changes in cinema.sql before we create a new one
 
CREATE TABLE movies(
    id SERIAL,
    title VARCHAR(255),
    duration INT, 
    bbfc_rating VARCHAR(255)
);
```

We can indicated constraints such as NOT NULL right after the data type if we do not allow missing values when inserting into table.

*Running sql file from command line:*

```
psql -d cinema -f cinema.sql 
```

This creates a table in the database cinema which we created through `createdb cinema`.

*Entering the database*
```
psql -d cinema
```

This leads to `cinema=#` where we can use the command `\dt` to show the relations in the database and list the tables.

### **Operations**

**C.R.U.D** format:

- Create - `INSERT INTO, VALUES`
- Read -`SELECT, FROM, WHERE, LIKE, ORDER BY ... etc.`
- Update - `UPDATE, SET, WHERE`
- Delete - `DELETE FROM, WHERE`

*cinema.sql*
```sql
DROP TABLE movies;

CREATE TABLE movies(
    id SERIAL,
    title VARCHAR(255),
    duration INT,
    bbfc_rating VARCHAR(255)
);

-- | --------- CREATE --------- |

INSERT INTO movies (title, duration, bbfc_rating) VALUES ('Alien', 117, '18');
INSERT INTO movies (title, duration, bbfc_rating) VALUES ('The Imitation Game', 114, '12A');
INSERT INTO movies (title, duration, bbfc_rating) VALUES ('Iron Man', 126, '12A');
INSERT INTO movies (title, duration, bbfc_rating) VALUES ('The Martian', 144, '12A');
INSERT INTO movies (title, bbfc_rating) VALUES ('Braveheart', 'PG'); -- still have an entry but the duration for Braveheart would be null



-- | --------- READ --------- |

SELECT * FROM movies WHERE LOWER(title) LIKE LOWER('%The%');
 -- % represents fuzzy parts before and after the word Martian

SELECT * FROM movies ORDER BY duration DESC; -- id is the tiebreaker, ASC is default, capital precedence to lower case

SELECT * FROM movies WHERE bbfc_rating = 'PG'; 

SELECT COUNT(*) FROM movies;

SELECT DISTINCT bbfc_rating FROM movies; -- finds unique values of bbfc_rating, however removes rest of the data
SELECT bbfc_rating, COUNT(*) FROM movies GROUP BY bbfc_rating; -- this groups all the data by bbfc_rating and allows COUNT for each group rather than remove rest of data

SELECT bbfc_rating, AVG(duration) FROM movies GROUP BY bbfc_rating;
SELECT bbfc_rating, SUM(duration) FROM movies GROUP BY bbfc_rating;


-- | --------- UPDATE --------- |
 
UPDATE movies SET (duration, bbfc_rating) = (178,'15') WHERE id = 5; -- most of the time we use id


-- | --------- DELETE --------- |

DELETE FROM movies WHERE id = 5;
```

**Multiple queries** are called a **transaction**

### **Order of Operations**

![Operations Order](/images/operations_order.png)

[Back to Top](#sql-cheatsheet)