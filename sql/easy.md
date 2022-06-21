These are answers to HackerRank's easy-leveled SQL challenges as of 06-21-2022. All answers are written in MySQL.

1. Query all columns for all American cities in the **CITY** table with populations larger than 100000. The **CountryCode** for America is USA. The **CITY** table is described as follows:

<img src = "https://s3.amazonaws.com/hr-challenge-images/8137/1449729804-f21d187d0f-CITY.jpg" width="200">

```
SELECT * FROM CITY WHERE (POPULATION > 100000) AND (COUNTRYCODE = "USA");
```

2. Query all columns (attributes) for every row in the **CITY** table. The **CITY** table is described as follows:

<img src = "https://s3.amazonaws.com/hr-challenge-images/8137/1449729804-f21d187d0f-CITY.jpg" width="200">

```
SELECT * FROM CITY;
```

4. Query all columns for a city in **CITY** with the **ID** 1661. The **CITY** table is described as follows:

<img src = "https://s3.amazonaws.com/hr-challenge-images/8137/1449729804-f21d187d0f-CITY.jpg" width="200">

```
SELECT * FROM CITY WHERE ID = '1661';
```

5. Query all attributes of every Japanese city in the **CITY** table. The **COUNTRYCODE** for Japan is JPN. The **CITY** table is described as follows:

<img src = "https://s3.amazonaws.com/hr-challenge-images/8137/1449729804-f21d187d0f-CITY.jpg" width="200">

```
SELECT * FROM CITY WHERE COUNTRYCODE = 'JPN';
```

6. Query the names of all the Japanese cities in the **CITY** table. The **COUNTRYCODE** for Japan is JPN. The **CITY** table is described as follows:

<img src = "https://s3.amazonaws.com/hr-challenge-images/8137/1449729804-f21d187d0f-CITY.jpg" width="200">

```
SELECT NAME FROM CITY WHERE (COUNTRYCODE = 'JPN');
```

7. Query a list of **CITY** and **STATE** from the **STATION** table. The **STATION** table is described as follows:

<img src = "https://s3.amazonaws.com/hr-challenge-images/9336/1449345840-5f0a551030-Station.jpg" width="200">

where **LAT_N** is the northern latitude and **LONG_W** is the western longitude.

```
SELECT CITY, STATE FROM STATION;
```

8. Query a list of **CITY** names from **STATION** for cities that have an even **ID** number. Print the results in any order, but exclude duplicates from the answer. The **STATION** table is described as follows:

<img src = "https://s3.amazonaws.com/hr-challenge-images/9336/1449345840-5f0a551030-Station.jpg" width="200">

where **LAT_N** is the northern latitude and **LONG_W** is the western longitude.

```
SELECT DISTINCT CITY FROM STATION WHERE (ID%2 = 0);
```

9. Find the difference between the total number of **CITY** entries in the table and the number of distinct **CITY** entries in the table. The **STATION** table is described as follows:

<img src = "https://s3.amazonaws.com/hr-challenge-images/9336/1449345840-5f0a551030-Station.jpg" width="200">

where **LAT_N** is the northern latitude and **LONG_W** is the western longitude.

For example, if there are three records in the table with CITY values 'New York', 'New York', 'Bengalaru', there are 2 different city names: 'New York' and 'Bengalaru'. The query returns $1$, because $N_{records} - N_{distinct} = 3 - 2 = 1$.

```
SELECT COUNT(CITY) - COUNT(DISTINCT CITY) FROM STATION;
```
