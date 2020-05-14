# SQL-Tuning-1

# TIÊU CÔNG HÒA

# Bài 1: Viết lệnh SQL từ kết quả EXPLAIN ANALYZE

# Yêu cầu 1:
```sql
EXPLAIN ANALYZE 
SELECT actor.actor_id, actor.first_name, actor.last_name, actor.last_update
FROM actor;
```
# Yêu cầu 2:
```sql
EXPLAIN ANALYZE 
SELECT actor.first_name, actor.last_name
FROM actor
WHERE actor.first_name = 'Nick';
```
# Yêu cầu 3:
```sql
EXPLAIN ANALYZE 
SELECT actor.actor_id, actor.first_name, actor.last_name, actor.last_update
FROM actor
WHERE actor.actor_id = 100
ORDER BY actor.first_name, actor.last_name;
```
# Yêu cầu 4:
```sql
EXPLAIN ANALYZE 
SELECT film.rating, COUNT(film_id)
FROM film
WHERE film.length > 100
GROUP BY film.rating
ORDER BY film.rating DESC;
```
# Yêu cầu 5:
```sql
EXPLAIN ANALYZE 
SELECT city.city, country.country
FROM city 
INNER JOIN country
ON city.country_id = country.country_id;
```
# Yêu cầu 6:
```sql
EXPLAIN ANALYZE 
SELECT film.title, film.description, film.rating, film.length,
(
	SELECT AVG(rating_avg.length)
	FROM film rating_avg
	WHERE film.rating = rating_avg.rating
	GROUP BY rating_avg.rating
)
FROM film
ORDER BY film.rating;
```
