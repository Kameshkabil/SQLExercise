# Exercise1

### 1.Find the title of each film 
```sql
SELECT title FROM movies;
```
### 2.Find the director of each film 
```sql
SELECT director FROM movies;
```

### 3.Find the title and director of each film
```sql
SELECT title,director FROM movies;
```

### 4.Find the title and year of each film 
```sql
SELECT title,year FROM movies;
```

### 5.Find all the information about each film
```sql
SELECT * FROM movies;
```

# Exercise2 :

### 1.Find the movie with a row id of 6 
```sql
SELECT * FROM movies WHERE id=6;
```

### 2.Find the movies released in the years between 2000 and 2010 
```sql
SELECT * FROM movies WHERE year BETWEEN 2000 AND 2010;
```

### 3.Find the movies not released in the years between 2000 and 2010 
```sql 
SELECT * FROM movies WHERE year  NOT BETWEEN  2000 AND 2010;
```

### 4.Find the first 5 Pixar movies and their release year 
```sql 
SELECT * FROM movies LIMIT 5;
```

# exercise 3:

### 1.Find all the Toy Story movies 
```sql
SELECT title FROM movies WHERE title LIKE "TOY%";
```

### 2.Find all the movies directed by John Lasseter
```sql
SELECT * FROM movies WHERE director='John Lasseter';
```

### 3.Find all the movies (and director) not directed by John Lasseter
```sql
SELECT * FROM movies WHERE director!="John Lasseter";
```

### 4.Find all the WALL-* movies
```sql
select title from Movies where title like 'WALL%'
```

# exercise4:

### 1.List all directors of Pixar movies (alphabetically), without duplicates 
```sql
SELECT DISTINCT(director) FROM movies ORDER BY director ASC;
```

### 2.List the last four Pixar movies released (ordered from most recent to least) 
```sql
SELECT * FROM movies ORDER BY year DESC LIMIT 4;
```

### 3.List the first five Pixar movies sorted alphabetically 
```sql
select title from movies order by title asc limit 5;
```

### 4.List the next five Pixar movies sorted alphabetically 
```sql
SELECT title FROM movies ORDER BY title ASC LIMIT 5,5 ;
```

# exercise 5:

### 1.List all the Canadian cities and their populations 
```sql
SELECT CITY , POPULATION FROM north_american_cities WHERE country='Canada'
```

### 2.Order all the cities in the United States by their latitude from north to south 
```sql
SELECT city FROM north_american_cities where country ='United States' order by latitude desc;
```

### 3.List all the cities west of Chicago, ordered from west to east 
```sql
select city from North_american_cities where longitude< 
(select Longitude from North_american_cities where city = 'Chicago' ) 
order by longitude asc;
```

### 4.List the two largest cities in Mexico (by population)
```sql
SELECT * FROM north_american_cities where country='Mexico' order by population desc limit 2;
```

### 5.List the third and fourth largest cities (by population) in the United States and their population 
```sql
SELECT * FROM north_american_cities where country='United States' order by population desc limit 2,2;
```

# exercise 6:

### 1.Find the domestic and international sales for each movie 
```sql
SELECT title,domestic_sales,international_sales FROM movies inner join boxoffice on movies.id=boxoffice.movie_id;
```

### 2.Show the sales numbers for each movie that did better internationally rather than domestically 
```sql ans:select title, Domestic_sales, International_sales from Movies inner join 
Boxoffice on Movies.Id = Boxoffice.Movie_id 
where International_sales>Domestic_sales order by International_sales desc;
```

### 3.List all the movies by their ratings in descending order 
```sql
SELECT * FROM movies inner join boxoffice on movies.id=boxoffice.movie_id
 order by boxoffice.rating desc;
```

# exercise 13:

### 1.Add the studio's new production, Toy Story 4 to the list of movies (you can use any director) 
```sql
insert into movies (title,director) values ('Toy Story5','John Lasseter');
```

# exercise 14:

### 1.The director for A Bug's Life is incorrect, it was actually directed by John Lasseter 
```sql
update movies set director = 'John Lasseter' where title="A Bug's Life";
```

### 2.The year that Toy Story 2 was released is incorrect, it was actually released in 1999 
```sql
update movies set year = 1999 where title = 'Toy Story 2'
```

### 3.Both the title and director for Toy Story 8 is incorrect! The title should be "Toy Story 3" and it was directed by Lee Unkrich 
```sql
Update Movies set Title = 'Toy Story 3', Director = 'Lee Unkrich' 
where Title = 'Toy Story 8';
```

# exercise 15:
### 1.This database is getting too big, lets remove all movies that were released before 2005
```sql
delete from movies where year < 2005;
```

### 2.Andrew Stanton has also left the studio, so please remove all movies directed by him.
```sql
delete from movies where director="Andrew Stanton"
```

# exercise 16:
### 1.Create a new table named Database with the following columns: – Name A string (text) describing the name of the database – Version A number (floating point) of the latest version of this database – Download_count An integer count of the number of times this database was downloadedThis table has no constraints. 

```sql
create table database(
    name varchar(45),
    version float,
    download_count int
)
```

# exercise 17:
### 1.Add a column named Aspect_ratio with a FLOAT data type to store the aspect-ratio each movie was released in.
```sql
alter table movies add Aspect_ratio float;
```

### 2.Add another column named Language with a TEXT data type to store the language that the movie was released in. Ensure that the default for this language is English.
```sql
alter table movies add language varchar(30) default 'English'
```

# exercise 18:
### 1.We've sadly reached the end of our lessons, lets clean up by removing the Movies table
```sql
drop table movies;
```

### 2.And drop the BoxOffice table as well.
```sql
drop table boxoffice;
```
