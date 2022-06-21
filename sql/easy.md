1. Query all columns for all American cities in the **CITY** table with populations larger than 100000. The **CountryCode** for America is USA. The **CITY** table is described as follows:

<img src = "https://s3.amazonaws.com/hr-challenge-images/8137/1449729804-f21d187d0f-CITY.jpg" width="250">

```
SELECT * FROM CITY WHERE (POPULATION > 100000) AND (COUNTRYCODE = "USA");
```

2. Query all columns (attributes) for every row in the **CITY** table. The **CITY** table is described as follows:

<img src = "https://s3.amazonaws.com/hr-challenge-images/8137/1449729804-f21d187d0f-CITY.jpg" width="250">

```
SELECT * FROM CITY;
```

4. Query all columns for a city in **CITY** with the **ID** 1661. The **CITY** table is described as follows:

<img src = "https://s3.amazonaws.com/hr-challenge-images/8137/1449729804-f21d187d0f-CITY.jpg" width="250">

```
SELECT * FROM CITY WHERE (ID = "1661);
```

5. 
