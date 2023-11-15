Exercise1 :

1.Find the title of each film 

ans: SELECT title FROM movies;

2.Find the director of each film 

ans: SELECT director FROM movies;

3.Find the title and director of each film

ans:SELECT title,director FROM movies;

4.Find the title and year of each film 

ans: SELECT title,year FROM movies;

5.Find all the information about each film

ans:SELECT * FROM movies;

Exercise2 :
1.Find the movie with a row id of 6 

ans:SELECT * FROM movies WHERE id=6;

2.Find the movies released in the years between 2000 and 2010 

ans:SELECT * FROM movies WHERE year BETWEEN 2000 AND 2010;

3.Find the movies not released in the years between 2000 and 2010 

ans:SELECT * FROM movies WHERE year  NOT BETWEEN  2000 AND 2010;

4.Find the first 5 Pixar movies and their release year 

exercise 3:
--------------------------------------------------------------
1.Find all the Toy Story movies 
ans: SELECT title FROM movies WHERE title LIKE "TOY%";

2.Find all the movies directed by John Lasseter
ans:SELECT * FROM movies WHERE director='John Lasseter';

3.Find all the movies (and director) not directed by John Lasseter
ans:SELECT * FROM movies WHERE director!="John Lasseter";

4.Find all the WALL-* movies
ans:select title from Movies where title like 'WALL%'

ans: SELECT * FROM movies LIMIT 5;

exercise4:
--------------------------------------------------------------------------
1.List all directors of Pixar movies (alphabetically), without duplicates 
ans:SELECT DISTINCT(director) FROM movies ORDER BY director ASC;

2.List the last four Pixar movies released (ordered from most recent to least) 
ans:SELECT * FROM movies ORDER BY year DESC LIMIT 4;

3.List the first five Pixar movies sorted alphabetically 
ans: select title from movies order by title asc limit 5;

4.List the next five Pixar movies sorted alphabetically 
ans:SELECT title FROM movies ORDER BY title ASC LIMIT 5,5 ;

exercise 5:
---------------------------------------------------------------------------------------
1.List all the Canadian cities and their populations 
ans:SELECT CITY , POPULATION FROM north_american_cities WHERE country='Canada'

2.Order all the cities in the United States by their latitude from north to south 
ans:SELECT city FROM north_american_cities where country ='United States' order by latitude desc;

3.List all the cities west of Chicago, ordered from west to east 
ans:select city from North_american_cities where longitude< 
(select Longitude from North_american_cities where city = 'Chicago' ) 
order by longitude asc;

4.List the two largest cities in Mexico (by population)
ans:SELECT * FROM north_american_cities where country='Mexico' order by population desc limit 2;

5.List the third and fourth largest cities (by population) in the United States and their population 
ans:SELECT * FROM north_american_cities where country='United States' order by population desc limit 2,2;

exercise 6:
--------------------------------------------------------------------------------------
1.Find the domestic and international sales for each movie 
ans:SELECT title,domestic_sales,international_sales FROM movies inner join boxoffice on movies.id=boxoffice.movie_id;

2.Show the sales numbers for each movie that did better internationally rather than domestically 
ans:select title, Domestic_sales, International_sales from Movies inner join 
Boxoffice on Movies.Id = Boxoffice.Movie_id 
where International_sales>Domestic_sales order by International_sales desc;

3.List all the movies by their ratings in descending order 
ans:SELECT * FROM movies inner join boxoffice on movies.id=boxoffice.movie_id
 order by boxoffice.rating desc;
