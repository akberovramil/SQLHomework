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
WHERE first_name LIKE '_____%';

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
SELECT first_name AS Неуникальное_имя,
age AS Возраст
FROM employee
WHERE NOT first_name = 'Maria'
ORDER BY age ASC;