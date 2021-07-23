# SQL_Solutions_HackerRank

## 1. Revising the Select Query I 

Query all columns for all American cities in the CITY table with populations larger than 100000. The CountryCode for America is USA.

The CITY table is described as follows:

| FIELD | TYPE |
| --- | --- |
| ID | NUMBER |
| NAME | VARCHAR(17) |
| COUNTRYCODE | VARCHAR(3) |
| DISTRICT | VARCHAR(20) |
| POPULATION | NUMBER |

### Solution :
     SELECT * FROM CITY WHERE COUNTRYCODE="USA" AND  POPULATION>100000;
     
## 2. Revising the Select Query II

Query the NAME field for all American cities in the CITY table with populations larger than 120000. The CountryCode for America is USA.

The CITY table is described as follows:

| FIELD | TYPE |
| --- | --- |
| ID | NUMBER |
| NAME | VARCHAR(17) |
| COUNTRYCODE | VARCHAR(3) |
| DISTRICT | VARCHAR(20) |
| POPULATION | NUMBER |

### Solution :
     SELECT NAME FROM CITY WHERE COUNTRYCODE="USA" AND POPULATION>120000;
     
## 3. Select All

Query all columns (attributes) for every row in the CITY table.

The CITY table is described as follows:

| FIELD | TYPE |
| --- | --- |
| ID | NUMBER |
| NAME | VARCHAR(17) |
| COUNTRYCODE | VARCHAR(3) |
| DISTRICT | VARCHAR(20) |
| POPULATION | NUMBER |

### Solution :
     SELECT * FROM CITY;

## 4. Select By ID

Query all columns for a city in CITY with the ID 1661.

The CITY table is described as follows:

| FIELD | TYPE |
| --- | --- |
| ID | NUMBER |
| NAME | VARCHAR(17) |
| COUNTRYCODE | VARCHAR(3) |
| DISTRICT | VARCHAR(20) |
| POPULATION | NUMBER |

### Solution :
     SELECT * FROM CITY WHERE ID=1661;

## 5. Japanese Cities' Attributes

Query all attributes of every Japanese city in the CITY table. The COUNTRYCODE for Japan is JPN.

The CITY table is described as follows:

| FIELD | TYPE |
| --- | --- |
| ID | NUMBER |
| NAME | VARCHAR(17) |
| COUNTRYCODE | VARCHAR(3) |
| DISTRICT | VARCHAR(20) |
| POPULATION | NUMBER |

### Solution :
     SELECT * FROM CITY WHERE COUNTRYCODE="JPN";

## 6. Japanese Cities' Names

Query the names of all the Japanese cities in the CITY table. The COUNTRYCODE for Japan is JPN.
The CITY table is described as follows:

| FIELD | TYPE |
| --- | --- |
| ID | NUMBER |
| NAME | VARCHAR(17) |
| COUNTRYCODE | VARCHAR(3) |
| DISTRICT | VARCHAR(20) |
| POPULATION | NUMBER |

### Solution :
     SELECT NAME FROM CITY WHERE COUNTRYCODE="JPN";

## 7. Weather Observation Station 1

Query a list of CITY and STATE from the STATION table.
The STATION table is described as follows:


| FIELD | TYPE |
| --- | --- |
| ID | NUMBER |
| CITY | VARCHAR(21) |
| STATE | VARCHAR(2) |
| LAT_N | NUMBER |
| LONG_W | NUMBER |

where LAT_N is the northern latitude and LONG_W is the western longitude.

### Solution :
     SELECT CITY, STATE FROM STATION;

## 8. Weather Observation Station 3

Query a list of CITY names from STATION for cities that have an even ID number. Print the results in any order, but exclude duplicates from the answer.
The STATION table is described as follows:

| FIELD | TYPE |
| --- | --- |
| ID | NUMBER |
| CITY | VARCHAR(21) |
| STATE | VARCHAR(2) |
| LAT_N | NUMBER |
| LONG_W | NUMBER |

where LAT_N is the northern latitude and LONG_W is the western longitude.

### Solution :
     SELECT DISTINCT CITY FROM STATION WHERE ID%2=0;

## 9. Weather Observation Station 4

Find the difference between the total number of CITY entries in the table and the number of distinct CITY entries in the table.
The STATION table is described as follows:

| FIELD | TYPE |
| --- | --- |
| ID     | NUMBER |
| CITY   | VARCHAR(21) |
| STATE  | VARCHAR(2) |
| LAT_N  | NUMBER |
| LONG_W | NUMBER |

where LAT_N is the northern latitude and LONG_W is the western longitude.

### Solution :
     SELECT COUNT(CITY)- COUNT(DISTINCT CITY) FROM STATION;

## 10. Employee Salaries

Write a query that prints a list of employee names (i.e.: the name attribute) for employees in Employee having a salary greater than $200 per month who have been employees for less than  months. Sort your result by ascending employee_id.

Input Format

The Employee table containing employee data for a company is described as follows:

| Column      | Type    |
|-------------|---------|
| Employee_id | Integer |
| name        | String  |
| months      | Integer |
| salary      | Integer |

where employee_id is an employee's ID number, name is their name, months is the total number of months they've been working for the company, and salary is the their monthly salary.

### Solution :
     SELECT name FROM Employee WHERE salary>2000 AND months<10 ORDER BY employee_id ASC;
     
## 11. Employee Names

Write a query that prints a list of employee names (i.e.: the name attribute) from the Employee table in alphabetical order.

Input Format

The Employee table containing employee data for a company is described as follows:

| Column      | Type    |
|-------------|---------|
| Employee_id | Integer |
| name        | String  |
| months      | Integer |
| salary      | Integer |

where employee_id is an employee's ID number, name is their name, months is the total number of months they've been working for the company, and salary is their monthly salary.

### Solution :
     SELECT name FROM Employee ORDER BY name ASC;

## 12. Weather Observation Station 5

Query the two cities in STATION with the shortest and longest CITY names, as well as their respective lengths (i.e.: number of characters in the name). If there is more than one smallest or largest city, choose the one that comes first when ordered alphabetically.

The STATION table is described as follows:

| FIELD | TYPE |
| --- | --- |
| ID     | NUMBER |
| CITY   | VARCHAR(21) |
| STATE  | VARCHAR(2) |
| LAT_N  | NUMBER |
| LONG_W | NUMBER |

where LAT_N is the northern latitude and LONG_W is the western longitude.

### Solution :
     SELECT CITY, LENGTH(CITY) FROM STATION ORDER BY LENGTH(CITY),CITY ASC LIMIT 1;
     SELECT CITY, LENGTH(CITY) FROM STATION ORDER BY LENGTH(CITY) DESC LIMIT 1;

## 13. Weather Observation Station 9

Query the list of CITY names from STATION that do not start with vowels. Your result cannot contain duplicates.

Input Format

The STATION table is described as follows:

| FIELD | TYPE |
| --- | --- |
| ID     | NUMBER |
| CITY   | VARCHAR(21) |
| STATE  | VARCHAR(2) |
| LAT_N  | NUMBER |
| LONG_W | NUMBER |

where LAT_N is the northern latitude and LONG_W is the western longitude.

### Solution :
     SELECT DISTINCT CITY FROM STATION WHERE CITY REGEXP "^[^aeiou]";
     
     (OR) We can use below query also for this question
     
     SELECT DISTINCT CITY FROM STATION WHERE CITY REGEXP "^[bcdfghjklmnpqrstvwxyz]";

## 14. Weather Observation Station 7

Query the list of CITY names ending with vowels (a, e, i, o, u) from STATION. Your result cannot contain duplicates.

Input Format

The STATION table is described as follows:

| FIELD | TYPE |
| --- | --- |
| ID     | NUMBER |
| CITY   | VARCHAR(21) |
| STATE  | VARCHAR(2) |
| LAT_N  | NUMBER |
| LONG_W | NUMBER |

where LAT_N is the northern latitude and LONG_W is the western longitude.

### Solution :
     SELECT DISTINCT CITY FROM STATION WHERE CITY REGEXP "[aeiou]$";

## 15. Weather Observation Station 6

Query the list of CITY names starting with vowels (i.e., a, e, i, o, or u) from STATION. Your result cannot contain duplicates.

Input Format

The STATION table is described as follows:

| FIELD | TYPE |
| --- | --- |
| ID     | NUMBER |
| CITY   | VARCHAR(21) |
| STATE  | VARCHAR(2) |
| LAT_N  | NUMBER |
| LONG_W | NUMBER |

where LAT_N is the northern latitude and LONG_W is the western longitude.

### Solution :
     SELECT CITY FROM STATION WHERE CITY REGEXP "^[aeiou]";

## 16. Weather Observation Station 8

Query the list of CITY names from STATION which have vowels (i.e., a, e, i, o, and u) as both their first and last characters. Your result cannot contain duplicates.

Input Format

The STATION table is described as follows:

| FIELD | TYPE |
| --- | --- |
| ID     | NUMBER |
| CITY   | VARCHAR(21) |
| STATE  | VARCHAR(2) |
| LAT_N  | NUMBER |
| LONG_W | NUMBER |

where LAT_N is the northern latitude and LONG_W is the western longitude.

### Solution :
     SELECT CITY FROM STATION WHERE CITY REGEXP "^[aeiou]" AND CITY REGEXP "[aeiou]$";

## 17. Weather Observation Station 10

Query the list of CITY names from STATION that do not end with vowels. Your result cannot contain duplicates.

Input Format

The STATION table is described as follows:


| FIELD | TYPE |
| --- | --- |
| ID     | NUMBER |
| CITY   | VARCHAR(21) |
| STATE  | VARCHAR(2) |
| LAT_N  | NUMBER |
| LONG_W | NUMBER |

where LAT_N is the northern latitude and LONG_W is the western longitude.

### Solution :
     SELECT DISTINCT CITY FROM STATION WHERE CITY REGEXP "[^aeiou]$";


## 18. Weather Observation Station 11

Query the list of CITY names from STATION that either do not start with vowels or do not end with vowels. Your result cannot contain duplicates.

Input Format

The STATION table is described as follows:


| FIELD | TYPE |
| --- | --- |
| ID     | NUMBER |
| CITY   | VARCHAR(21) |
| STATE  | VARCHAR(2) |
| LAT_N  | NUMBER |
| LONG_W | NUMBER |

where LAT_N is the northern latitude and LONG_W is the western longitude.

### Solution :
     SELECT DISTINCT CITY FROM STATION WHERE CITY REGEXP "^[^aeiou]" OR CITY REGEXP "[^aeiou]$";

## 19. Weather Observation Station 12

Query the list of CITY names from STATION that do not start with vowels and do not end with vowels. Your result cannot contain duplicates.

Input Format

The STATION table is described as follows:

| FIELD | TYPE |
| --- | --- |
| ID     | NUMBER |
| CITY   | VARCHAR(21) |
| STATE  | VARCHAR(2) |
| LAT_N  | NUMBER |
| LONG_W | NUMBER |

where LAT_N is the northern latitude and LONG_W is the western longitude.

### Solution :
     SELECT DISTINCT CITY FROM STATION WHERE CITY REGEXP "^[^aeiou]" AND CITY REGEXP "[^aeiou]$";

## 20. Japan Population

Query the sum of the populations for all Japanese cities in CITY. The COUNTRYCODE for Japan is JPN.

Input Format

The CITY table is described as follows:

| FIELD | TYPE |
| --- | --- |
| ID     | NUMBER |
| NAME   | VARCHAR(17) |
| COUNTRYCODE  | VARCHAR(3) |
| DISTRICT  | VARCHAR(20) |
| POPULATION | NUMBER |

### Solution :
     SELECT SUM(POPULATION) FROM CITY WHERE COUNTRYCODE="JPN";

## 21. Japan Population

Query the difference between the maximum and minimum populations in CITY.

Input Format

The CITY table is described as follows:

| FIELD | TYPE |
| --- | --- |
| ID     | NUMBER |
| NAME   | VARCHAR(17) |
| COUNTRYCODE  | VARCHAR(3) |
| DISTRICT  | VARCHAR(20) |
| POPULATION | NUMBER |

### Solution :
     SELECT MAX(POPULATION) - MIN(POPULATION) FROM CITY;

## 22. Higher than 75 marks

Query the Name of any student in STUDENTS who scored higher than  Marks. Order your output by the last three characters of each name. If two or more students both have names ending in the same last three characters (i.e.: Bobby, Robby, etc.), secondary sort them by ascending ID.

### Solution :
     SELECT NAME FROM STUDENTS WHERE MARKS > 75 ORDER BY RIGHT(NAME, 3), ID ASC;

## 23. Revising Aggregations - The Sum Function

Query the total population of all cities in CITY where District is California.

Input Format

The CITY table is described as follows:

| FIELD | TYPE |
| --- | --- |
| ID     | NUMBER |
| NAME   | VARCHAR(17) |
| COUNTRYCODE  | VARCHAR(3) |
| DISTRICT  | VARCHAR(20) |
| POPULATION | NUMBER |

### Solution :
     SELECT SUM(POPULATION) FROM CITY WHERE DISTRICT="California";

## 24. Revising Aggregations - Averages

Query the average population of all cities in CITY where District is California.

Input Format

The CITY table is described as follows:

| FIELD | TYPE |
| --- | --- |
| ID     | NUMBER |
| NAME   | VARCHAR(17) |
| COUNTRYCODE  | VARCHAR(3) |
| DISTRICT  | VARCHAR(20) |
| POPULATION | NUMBER |

### Solution :
     SELECT AVG(POPULATION) FROM CITY WHERE DISTRICT="California";

## 25. Average Population

Query the average population for all cities in CITY, rounded down to the nearest integer.

Input Format

The CITY table is described as follows:

| FIELD | TYPE |
| --- | --- |
| ID     | NUMBER |
| NAME   | VARCHAR(17) |
| COUNTRYCODE  | VARCHAR(3) |
| DISTRICT  | VARCHAR(20) |
| POPULATION | NUMBER |

### Solution :
     SELECT ROUND(AVG(POPULATION)) FROM CITY;

## 26. Revising Aggregations - The Count Function

Query a count of the number of cities in CITY having a Population larger than 100,000.

Input Format

The CITY table is described as follows:

| FIELD | TYPE |
| --- | --- |
| ID     | NUMBER |
| NAME   | VARCHAR(17) |
| COUNTRYCODE  | VARCHAR(3) |
| DISTRICT  | VARCHAR(20) |
| POPULATION | NUMBER |

### Solution :
     SELECT COUNT(*) FROM CITY WHERE POPULATION>100000;
