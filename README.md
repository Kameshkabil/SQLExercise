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
---------------------------------------------------------------------
exercise 3:

1.Find all the Toy Story movies 
ans: SELECT title FROM movies WHERE title LIKE "TOY%";

2.Find all the movies directed by John Lasseter
ans:SELECT * FROM movies WHERE director='John Lasseter';

3.Find all the movies (and director) not directed by John Lasseter
ans:SELECT * FROM movies WHERE director!="John Lasseter";

4.Find all the WALL-* movies
ans:select title from Movies where title like 'WALL%'

ans: SELECT * FROM movies LIMIT 5;
