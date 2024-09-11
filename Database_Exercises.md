# Yhteen tauluun kohdistuvien kyselyiden harjoitukset

### Tehtävä 1
SELECT * FROM goal; 
![Tehtävä1](Images/Tentti2_Tehtävä1.png)

### Tehtävä 2
select name from airport where iso_country = "FI";

![Tehtävä2](Images/Tentti2_Tehtävä2.png)

### Tehtävä 3
SELECT name FROM airport WHERE iso_country = "FI" ORDER BY name ASC;

![Tehtävä3]{Images/Tentti2_Tehtävä3.png}

### Tehtävä 4
SELECT name, type FROM airport WHERE iso_country = "FI" ORDER BY type ASC, name ASC;

![Tehtävä4]{Images/Tentti2_Tehtävä4.png}

### Tehtävä 5
SELECT name FROM country WHERE name LIKE 'F%';

![Tehtävä5]{Images/Tentti2_Tehtävä5.png}

### Tehtävä 6
SELECT name FROM country WHERE name LIKE '%F%';

![Tehtävä6]{Images/Tentti2_Tehtävä6.png}

### Tehtävä 7
SELECT location FROM game WHERE screen_name = 'Vesa';

![Tehtävä7]{Images/Tentti2_Tehtävä7.png}

### Tehtävä 8
SELECT co2_consumed FROM game WHERE screen_name = 'Ilkka';

![Tehtävä8]{Images/Tentti2_Tehtävä8.png}

### Tehtävä 9
select co2_budget from game where screen_name = "Ilkka";

![Tehtävä9]{Images/Tentti2_Tehtävä9.png}
