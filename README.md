# HomeWork
1.
EXPLAIN (verbose) 
SELECT actor_id, first_name, last_name, last_update
FROM actor

2.
EXPLAIN (verbose) 
SELECT first_name, last_name
FROM actor
WHERE actor.first_name = 'Nick'

3. 
EXPLAIN (verbose) 
SELECT first_name, last_name
FROM actor
WHERE actor.actor_id = 100
ORDER BY actor.first_name, actor.last_name

4.
EXPLAIN (verbose) 
SELECT rating, (count(film_id))
FROM film
WHERE film.length > 100
GROUP BY film.rating
ORDER BY film.rating DESC

5.
EXPLAIN (verbose) SELECT city.city, country.country
FROM city
JOIN country
	ON city.country_id = country.country_id

6.
EXPLAIN (verbose) SELECT film.title, film.description, film.rating, film.length, 
	(SELECT avg(rating_avg.length), rating_avg.rating
	FROM film AS rating_avg
	WHERE film.rating = rating_avg.rating
	GROUP BY rating_avg.rating)
FROM film
ORDER BY film.rating
