ЗАДАНИЕ 1


INSERT INTO employee (
first_name, last_name, gender, age)
VALUES ('Petr', 'Alexeev', 'Men', 23);
INSERT INTO employee (
first_name, last_name, gender, age)
VALUES ('Nail', 'Alishev', 'Men', 27);
SELECT first_name AS Имя,
last_name AS Фамилия
FROM employee;
SELECT * FROM employee
WHERE age < 30 OR age > 50;
SELECT * FROM employee
WHERE age BETWEEN 30 AND 50;
SELECT * FROM employee
ORDER BY last_name DESC;
SELECT * FROM employee
WHERE length(first_name) > 4;

ЗАДАНИЕ 2

UPDATE employee
SET first_name = 'Ramill'
WHERE id = 1;
SELECT * FROM employee;
UPDATE employee
SET first_name = 'Ramill'
WHERE id = 6;
SELECT first_name AS Имя,
SUM(age) AS Суммарный_возраст
FROM employee
GROUP BY Имя;
SELECT first_name AS Имя,
MIN(age) AS Минимальный_возраст
FROM employee
GROUP BY Имя;
SELECT first_name,
max(age)
FROM employee
GROUP BY first_name HAVING count(first_name) > 1;

Домашнее задание 2

ЗАДАНИЕ 1

CREATE TABLE city (
city_id BIGSERIAL NOT NULL PRIMARY KEY,
city_name VARCHAR(60) NOT NULL
);
ALTER TABLE employee ADD COLUMN city_id BIGSERIAL NOT NULL;
ALTER TABLE employee ADD FOREIGN KEY(city_id) REFERENCES city(city_id);
INSERT INTO city (
city_name)
VALUES('Kazan');
SELECT * FROM employee
SELECT * FROM city
INSERT INTO city (
city_name)
VALUES('Ufa');
SELECT city_name, first_name, last_name
FROM city
INNER JOIN employee
ON city.city_id=employee.city_id;

Задание 2

SELECT first_name, last_name, city_name
FROM employee
INNER JOIN city
ON city.city_id=employee.city_id;
INSERT INTO city (
city_name)
VALUES('Niznekamsk');
SELECT city_name, first_name, last_name
FROM city
LEFT JOIN employee
ON city.city_id=employee.city_id;
SELECT city_name, first_name
FROM city
FULL JOIN employee
ON city.city_id=employee.city_id;
SELECT city_name, first_name
FROM city
CROSS JOIN employee;