-- 1. Покажите фамилию и имя клиентов из города Прага (Prague)
SELECT LastName, FirstName
FROM customers
WHERE City = 'Prague';

-- 2. Покажите фамилию и имя клиентов, у которых имя начинается на букву M или содержит символ "ch"
SELECT LastName, FirstName
FROM customers
WHERE FirstName LIKE 'M%' OR FirstName LIKE '%ch%';

-- 3. Покажите название и размер музыкальных треков в Мегабайтах
SELECT Name, Bytes / 1048576 AS Size_MB
FROM tracks;

-- 4. Покажите фамилию и имя сотрудников, нанятых в 2002 году из города Калгари (Calgary)
SELECT LastName, FirstName
FROM employees
WHERE City = 'Calgary' AND strftime('%Y', HireDate) = '2002';

-- 5. Покажите фамилию и имя сотрудников кампании, которым 40 лет и выше
SELECT LastName, FirstName
FROM employees
WHERE (strftime('%Y', 'now') - strftime('%Y', BirthDate)) >= 40;

-- 6. Покажите покупателей-американцев без факса
SELECT LastName, FirstName
FROM customers
WHERE Country = 'USA' AND Fax IS NULL;

-- 7. Покажите канадские города, в которые были продажи в августе и сентябре (Canada)
SELECT DISTINCT ShipCity
FROM sales
WHERE ShipCountry = 'Canada' AND strftime('%m', SalesDate) IN ('08', '09');

-- 8. Покажите почтовые адреса клиентов из домена gmail.com
SELECT Email
FROM customers
WHERE Email LIKE '%@gmail.com';

-- 9. Покажите сотрудников, которые работают в компании уже 18 лет и более
SELECT LastName, FirstName
FROM employees
WHERE (strftime('%Y', 'now') - strftime('%Y', HireDate)) >= 18;

-- 10. Покажите в алфавитном порядке все должности в компании
SELECT DISTINCT Title
FROM employees
ORDER BY Title;

-- 11. Покажите в алфавитном порядке Фамилию, Имя и год рождения покупателей
SELECT LastName, FirstName, strftime('%Y', BirthDate) AS BirthYear
FROM customers
ORDER BY LastName, FirstName;

-- 12. Сколько секунд длится самая короткая песня?
SELECT MIN(Milliseconds) / 1000.0 AS Shortest_Duration_Seconds
FROM tracks;

-- 13. Покажите название и длительность в секундах самой короткой песни
SELECT Name, MIN(Milliseconds) / 1000.0 AS Shortest_Duration_Seconds
FROM tracks;

-- 14. Покажите средний возраст клиента для каждой страны
SELECT Country, AVG(Age) AS Average_Age
FROM customers
GROUP BY Country;

-- 15. Покажите Фамилии работников, нанятых в октябре
SELECT LastName
FROM employees
WHERE strftime('%m', HireDate) = '10';

-- 16. Покажите фамилию самого старого по стажу сотрудника в компании
SELECT LastName
FROM employees
WHERE HireDate = (SELECT MIN(HireDate) FROM employees);
