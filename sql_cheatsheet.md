 # SQL Cheatsheet

# Table of Contents

0. [VS Code Tips](#vs-code-tips)
1. [Background](#background)
2. [Starting Up](#starting-up)
    * [Entity Relationship Diagrams](#entity-relationship-diagrams)
    * [Operations](#operations)
5. [Football Quiz](#football-quiz)
6. [SQL Relationships](#sql-relationships) 
    * [One to Many](#one-to-many)
    * [Many to Many](#many-to-many)
    * [One to One](#one-to-one)

## ***VS Code Tips***

|Command|Description|
|----|-----|
|`option` + `shift` + `down`|copies the current line down (same as `cmd + d` in IntelliJ)|
|`option` + [click multiple lines] |can edit multiple lines at the same time

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

## ***Football Quiz***

Each of the questions/tasks below can be answered using a `SELECT` query. When you find a solution copy it into the code block under the question before pushing your solution to GitHub.

1) Find all the matches from 2017.

```sql
SELECT * FROM matches WHERE season = 2017;
```

2) Find all the matches featuring Barcelona.

```sql
SELECT * FROM matches WHERE hometeam = 'Barcelona' OR awayteam = 'Barcelona';
```

3) What are the names of the Scottish divisions included?

```sql
SELECT name FROM divisions WHERE country = 'Scotland';
```

4) Find the value of the `code` for the `Bundesliga` division. Use that code to find out how many matches Freiburg have played in that division. HINT: You will need to query both tables

```sql
-- Two line solution
SELECT code FROM divisions WHERE name = 'Bundesliga';
SELECT COUNT(*) FROM matches WHERE division_code = ('D1') AND (hometeam = 'Freiburg' OR awayteam = 'Freiburg');

-- One line solution
SELECT COUNT(*) FROM matches WHERE division_code = (SELECT code FROM divisions WHERE name = 'Bundesliga') AND (hometeam = 'Freiburg' OR awayteam = 'Freiburg');
```

5) Find the teams which include the word "City" in their name. 

```sql
SELECT DISTINCT hometeam FROM matches WHERE LOWER(hometeam) LIKE LOWER('%City%');
```

6) How many different teams have played in matches recorded in a French division?

```sql
-- Two line solution
SELECT code FROM divisions WHERE country = 'France';
SELECT COUNT(DISTINCT hometeam) FROM matches WHERE division_code = ('F1') OR division_code = ('F2');

-- One line solution
SELECT COUNT(DISTINCT hometeam) FROM matches WHERE division_code in (SELECT code FROM divisions WHERE country = 'France');
```

7) Have Huddersfield played Swansea in any of the recorded matches?

```sql
SELECT COUNT(*) FROM matches WHERE (hometeam = 'Huddersfield' AND awayteam = 'Swansea') OR (hometeam = 'Swansea' AND awayteam = 'Huddersfield');
```

8) How many draws were there in the `Eredivisie` between 2010 and 2015?

```sql
SELECT COUNT(*) FROM matches WHERE division_code = (SELECT code FROM divisions WHERE name = 'Eredivisie') AND ftr = 'D' AND season BETWEEN 2010 AND 2015;
```

9) Select the matches played in the Premier League in order of total goals scored from highest to lowest. When two matches have the same total the match with more home goals should come first.

```sql
SELECT * FROM matches WHERE division_code = (SELECT code FROM divisions WHERE name = 'Premier League') ORDER BY (fthg + ftag) DESC, fthg DESC;
```

10) In which division and which season were the most goals scored?

```sql
SELECT division_code, divisions.name, season, SUM(fthg+ftag) FROM matches INNER JOIN divisions ON divisions.code = matches.division_code GROUP BY season, division_code, divisions.name ORDER BY SUM DESC LIMIT 1;
```

### Useful Resources

- [Filtering results](https://www.w3schools.com/sql/sql_where.asp)
- [Ordering results](https://www.w3schools.com/sql/sql_orderby.asp)
- [Grouping results](https://www.w3schools.com/sql/sql_groupby.asp)

## ***SQL Relationships***

Single Tables -
* Usually don't want database to consist of one massive table as fields grow
* How do we handle collections? SQL does not do array/arraylists

Multiple Tables -
* How do we maintain/handle relationships between them?
* SQL allows us to do this using **primary keys** and **foreign keys**
* We can even add extra tables to keep track of more complex relationships

Primary vs. Foreign Key - 
* The foreign key of a table (extra column) represents the primary key of another table
* e.g. adding a *director_id* column to the movies table which represents the directors table *id* column

### **One to Many**

![One to Many](/images/sql_one_to_many.png)

*movies_and_directors.sql*
```sql
DROP TABLE IF EXISTS movies;
DROP TABLE IF EXISTS directors; -- in this case, we have to drop the tables in the reverse order

CREATE TABLE directors( -- order matters, since directors is primary this table should come first
    id SERIAL PRIMARY KEY,
    name VARCHAR(255)
);

CREATE TABLE movies ( -- since movies references directors, this table comes second
    id SERIAL PRIMARY KEY, 
    title VARCHAR(255),
    duration INT,
    rating VARCHAR(255),
    director_id INT REFERENCES directors(id) -- foreign key which links to directors primary
);

INSERT INTO directors(name) VALUES ('Ridley Scott');
INSERT INTO directors(name) VALUES ('Morten Tyldum');
INSERT INTO directors(name) VALUES ('Jon Favreau');
INSERT INTO directors(name) VALUES ('Steven Spielberg');


INSERT INTO movies (title, duration, rating, director_id) VALUES ('Alien', 117, '18', 1);
INSERT INTO movies (title, duration, rating, director_id) VALUES ('The Imitation Game', 114, '12A', 2);
INSERT INTO movies (title, duration, rating, director_id) VALUES ('Iron Man', 126, '12A', 3);
INSERT INTO movies (title, duration, rating, director_id) VALUES ('The Martian', 144, '12A', 1);
```
### **Many to Many**

![Many to Many](/images/many_to_many.png)

*movies_and_directors.sql (continued)*
```sql
DROP TABLE IF EXISTS castings;
DROP TABLE IF EXISTS actors;

CREATE TABLE actors (
    id SERIAL PRIMARY KEY,
    name VARCHAR(255)
);

CREATE TABLE castings ( -- join table that has two foreign keys to maintain many to many
    id SERIAL PRIMARY KEY, -- films have many actors and actors have many films
    movie_id INT REFERENCES movies(id),
    actor_id INT REFERENCES actors(id),
    character_name VARCHAR(255)
);

-- INSERTS FOR BOTH
```

### **One to One**

Less common but you may wish to split up a big table into two. This may be because there is a lot of null errors in some parts of the data that you want to separate.

In order to implement a one to one, both tables have to have a foreign key. e.g. one table with usernames and email_id and the other table should have usernames_id and email.

Implementation of these are harder since during creation of table, there would be a table referencing the other which does not exist yet. Using an ORM (Object-Relational Mapping) tool like Hibernate handles this issue.

[Back to Top](#sql-cheatsheet)