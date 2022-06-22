These are answers to HackerRank's easy SQL challenges as of 06-21-2022. All answers are written in MySQL.

## Question #1

Query all columns for all American cities in the **CITY** table with populations larger than 100000. The **COUNTRYCODE** for America is `USA`. The **CITY** table is described as follows:

<img src = "https://s3.amazonaws.com/hr-challenge-images/8137/1449729804-f21d187d0f-CITY.jpg" width="200">

```
SELECT *
FROM CITY
WHERE (POPULATION > 100000) AND (COUNTRYCODE = "USA");
```

## Question #2

Query all columns (attributes) for every row in the **CITY** table. The **CITY** table is described as follows:

<img src = "https://s3.amazonaws.com/hr-challenge-images/8137/1449729804-f21d187d0f-CITY.jpg" width="200">

```
SELECT *
FROM CITY;
```

## Question #3

Query all columns for a city in **CITY** with the **ID** `1661`. The **CITY** table is described as follows:

<img src = "https://s3.amazonaws.com/hr-challenge-images/8137/1449729804-f21d187d0f-CITY.jpg" width="200">

```
SELECT *
FROM CITY
WHERE ID = '1661';
```

## Question #4

Query all attributes of every Japanese city in the **CITY** table. The **COUNTRYCODE** for Japan is `JPN`. The **CITY** table is described as follows:

<img src = "https://s3.amazonaws.com/hr-challenge-images/8137/1449729804-f21d187d0f-CITY.jpg" width="200">

```
SELECT *
FROM CITY
WHERE COUNTRYCODE = 'JPN';
```

## Question #5

Query the names of all the Japanese cities in the **CITY** table. The **COUNTRYCODE** for Japan is `JPN`. The **CITY** table is described as follows:

<img src = "https://s3.amazonaws.com/hr-challenge-images/8137/1449729804-f21d187d0f-CITY.jpg" width="200">

```
SELECT NAME
FROM CITY
WHERE (COUNTRYCODE = 'JPN');
```

## Question #6

Query a list of **CITY** and **STATE** from the **STATION** table. The **STATION** table is described as follows:

<img src = "https://s3.amazonaws.com/hr-challenge-images/9336/1449345840-5f0a551030-Station.jpg" width="200">

where **LAT_N** is the northern latitude and **LONG_W** is the western longitude.

```
SELECT CITY, STATE
FROM STATION;
```

## Question #7

Query a list of **CITY** names from **STATION** for cities that have an even **ID** number. Print the results in any order, but exclude duplicates from the answer. The **STATION** table is described as follows:

<img src = "https://s3.amazonaws.com/hr-challenge-images/9336/1449345840-5f0a551030-Station.jpg" width="200">

where **LAT_N** is the northern latitude and **LONG_W** is the western longitude.

```
SELECT DISTINCT CITY
FROM STATION
WHERE (ID%2 = 0);
```

## Question #8

Find the difference between the total number of **CITY** entries in the table and the number of distinct **CITY** entries in the table. The **STATION** table is described as follows:

<img src = "https://s3.amazonaws.com/hr-challenge-images/9336/1449345840-5f0a551030-Station.jpg" width="200">

where **LAT_N** is the northern latitude and **LONG_W** is the western longitude.

For example, if there are three records in the table with **CITY** values `New York`, `New York`, `Bengalaru`, there are 2 different city names: `New York` and `Bengalaru`. The query returns $1$, because $N_{records} - N_{distinct} = 3 - 2 = 1$.

```
SELECT COUNT(CITY) - COUNT(DISTINCT CITY)
FROM STATION;
```

## Question #9

Query the two cities in **STATION** with the shortest and longest **CITY** names, as well as their respective lengths (i.e.: number of characters in the name). If there is more than one smallest or largest city, choose the one that comes first when ordered alphabetically. The **STATION** table is described as follows:

<img src = "https://s3.amazonaws.com/hr-challenge-images/9336/1449345840-5f0a551030-Station.jpg" width="200">

where **LAT_N** is the northern latitude and **LONG_W** is the western longitude.

For example, **CITY** has four entries: `DEF`, `ABC`, `PQRS` and `WXY`.

**Sample Output**

```
ABC 3
PQRS 4
```

**Explanation**

When ordered alphabetically, the **CITY** names are listed as `ABC`, `DEF`, `PQRS`, and `WXY`, with lengths
$3, 3, 4$ and $3$. The longest name is `PQRS`, but there are $3$ options for shortest named city. Choose `ABC`, because it comes first alphabetically.

**Note**

You can write two separate queries to get the desired output. It need not be a single query.

```
SELECT CITY, LENGTH(CITY)
FROM STATION
ORDER BY LENGTH(CITY) ASC, CITY ASC
LIMIT 1;

SELECT CITY, LENGTH(CITY)
FROM STATION
ORDER BY LENGTH(CITY) DESC, CITY ASC
LIMIT 1;
```

## Question #10

Query the list of **CITY** names starting with vowels (i.e., a, e, i, o, or u) from **STATION**. Your result cannot contain duplicates. The **STATION** table is described as follows:

<img src = "https://s3.amazonaws.com/hr-challenge-images/9336/1449345840-5f0a551030-Station.jpg" width="200">

where **LAT_N** is the northern latitude and **LONG_W** is the western longitude.

```
SELECT DISTINCT CITY
FROM STATION
WHERE CITY REGEXP '[aeiou]$';
```

## Question #11

Query the list of **CITY** names from **STATION** which have vowels (i.e., a, e, i, o, and u) as both their first and last characters. Your result cannot contain duplicates. The **STATION** table is described as follows:

<img src = "https://s3.amazonaws.com/hr-challenge-images/9336/1449345840-5f0a551030-Station.jpg" width="200">

where **LAT_N** is the northern latitude and **LONG_W** is the western longitude.

```
SELECT DISTINCT CITY
FROM STATION
WHERE CITY REGEXP '^[aeiou].*[aeiou]$';
```

## Question #12

Query the list of **CITY** names from **STATION** that do not start with vowels. Your result cannot contain duplicates. The **STATION** table is described as follows:

<img src = "https://s3.amazonaws.com/hr-challenge-images/9336/1449345840-5f0a551030-Station.jpg" width="200">

where **LAT_N** is the northern latitude and **LONG_W** is the western longitude.

```
SELECT DISTINCT CITY
FROM STATION
WHERE CITY REGEXP '^[^aeiou].*';
```

## Question #13

Query the list of **CITY** names from **STATION** that do not end with vowels. Your result cannot contain duplicates. The **STATION** table is described as follows:

<img src = "https://s3.amazonaws.com/hr-challenge-images/9336/1449345840-5f0a551030-Station.jpg" width="200">

where **LAT_N** is the northern latitude and **LONG_W** is the western longitude.

```
SELECT DISTINCT CITY
FROM STATION
WHERE CITY REGEXP '[^aeiou]$';
```

## Question #14

Query the list of **CITY** names from **STATION** that either do not start or end with vowels. Your result cannot contain duplicates. The **STATION** table is described as follows:

<img src = "https://s3.amazonaws.com/hr-challenge-images/9336/1449345840-5f0a551030-Station.jpg" width="200">

where **LAT_N** is the northern latitude and **LONG_W** is the western longitude.

```
SELECT DISTINCT CITY
FROM STATION
WHERE CITY REGEXP '^[^aeiou].*|.*[^aeiou]$';
```

## Question #15

Query the list of **CITY** names from **STATION** that do not start and end with vowels. Your result cannot contain duplicates. The **STATION** table is described as follows:

<img src = "https://s3.amazonaws.com/hr-challenge-images/9336/1449345840-5f0a551030-Station.jpg" width="200">

where **LAT_N** is the northern latitude and **LONG_W** is the western longitude.

```
SELECT DISTINCT CITY
FROM STATION
WHERE CITY REGEXP '^[^aeiou].*[^aeiou]$';
```

## Question #16

Query the **Name** of any student in **STUDENTS** who scored higher than $75$ marks. Order your output by the last three characters of each name. If two or more students both have names ending in the same last three characters (i.e.: `Bobby`, `Robby`, etc.), secondary sort them by ascending **ID**. The **STUDENTS** table is described as follows:

<img src = "https://s3.amazonaws.com/hr-challenge-images/12896/1443815243-94b941f556-1.png" width="200">

The **Name** column only contains uppercase (A-Z) and lowercase (a-z) letters.

**Sample Input**

<img src = "https://s3.amazonaws.com/hr-challenge-images/12896/1443815209-cf4b260993-2.png" width="200">

**Sample Output**

```
Ashley
Julia
Belvet
```

**Explanation**

Only Ashley, Julia, and Belvet have > $75$ marks. If you look at the last three characters of each of their names, there are no duplicates and `'ley'` < `'lia'` < `'vet'`. 

```
SELECT NAME
FROM STUDENTS
WHERE (MARKS > 75)
ORDER BY RIGHT(NAME,3) ASC, ID ASC;
```

## Question #17

Write a query that prints a list of employee names (i.e.: the name attribute) from the **Employee** table in alphabetical order.  The **Employee** table containing employee data for a company is described as follows: 

<img src = "https://s3.amazonaws.com/hr-challenge-images/19629/1458557872-4396838885-ScreenShot2016-03-21at4.27.13PM.png" width="200">

where **employee_id** is an employee's ID number, **name** is their name, **months** is the total number of months they've been working for the company, and **salary** is their monthly salary.

**Sample Input**

<img src = "https://s3.amazonaws.com/hr-challenge-images/19629/1458558202-9a8721e44b-ScreenShot2016-03-21at4.32.59PM.png" width="200">

**Sample Output**

```
Angela
Bonnie
Frank
Joe
Kimberly
Lisa
Michael
Patrick
Rose
Todd
```

```
SELECT NAME
FROM EMPLOYEE
ORDER BY NAME ASC;
```


## Question #18
## Question #19
## Question #20
## Question #21
## Question #22
## Question #23
## Question #24
## Question #25
## Question #26
## Question #27
## Question #28
## Question #29
## Question #30
## Question #31
