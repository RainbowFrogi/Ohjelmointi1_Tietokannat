# Yhteen tauluun kohdistuvien kyselyiden harjoitukset

### Tehtävä 1
SELECT * FROM goal; 
![Tehtävä1](Images/Tentti2_Tehtävä1.png)

### Tehtävä 2
select name from airport where iso_country = "FI";

![Tehtävä2](Images/Tentti2_Tehtävä2.png)

### Tehtävä 3
SELECT name FROM airport WHERE iso_country = "FI" ORDER BY name ASC;

![Tehtävä3](Images/Tentti2_Tehtävä3.png)

### Tehtävä 4
SELECT name, type FROM airport WHERE iso_country = "FI" ORDER BY type ASC, name ASC;

![Tehtävä4](Images/Tentti2_Tehtävä4.png)

### Tehtävä 5
SELECT name FROM country WHERE name LIKE 'F%';

![Tehtävä5](Images/Tentti2_Tehtävä5.png)

### Tehtävä 6
SELECT name FROM country WHERE name LIKE '%F%';

![Tehtävä6](Images/Tentti2_Tehtävä6.png)

### Tehtävä 7
SELECT location FROM game WHERE screen_name = 'Vesa';

![Tehtävä7](Images/Tentti2_Tehtävä7.png)

### Tehtävä 8
SELECT co2_consumed FROM game WHERE screen_name = 'Ilkka';

![Tehtävä8](Images/Tentti2_Tehtävä8.png)

### Tehtävä 9
select distinct co2_budget from game;

![Tehtävä9](Images/Tentti2_Tehtävä9.png)





# WHERE-osan liitosehto harjoitukset

### Tehtävä 1
SELECT c.name AS "country name", a.name AS "airport name" FROM country c JOIN airport a ON c.iso_country = a.iso_country WHERE a.iso_country = 'IS';

![Tehtävä1](Images/Tentti3_Tehtävä1.png)

### Tehtävä 2
SELECT a.name AS "airport name" FROM airport a WHERE iso_country = 'FR' AND type = 'large_airport';

![Tehtävä2](Images/Tentti3_Tehtävä2.png)

### Tehtävä 3
where c.continent = a.continent AND c.name = "Antarctica"

![Tehtävä3](Images/Tentti3_Tehtävä3.png)

### Tehtävä 4
SELECT a.elevation_ft FROM airport a, game g WHERE a.gps_code = g.location AND g.screen_name = "Heini";

![Tehtävä4](Images/Tentti3_Tehtävä4.png)

### Tehtävä 5
SELECT a.elevation_ft * 0.3048 AS elevation_m FROM airport a, game g WHERE a.gps_code = g.location AND g.screen_name = "Heini";

![Tehtävä5](Images/Tentti3_Tehtävä5.png)

### Tehtävä 6
SELECT a.name FROM airport a, game g WHERE a.gps_code = g.location AND g.screen_name = "Ilkka";

![Tehtävä6](Images/Tentti3_Tehtävä6.png)

### Tehtävä 7
SELECT c.name FROM airport a, country c, game g WHERE a.gps_code = g.location AND a.iso_country = c.iso_country AND c.iso_country = "GB" AND g.screen_name = "Ilkka";

![Tehtävä7](Images/Tentti3_Tehtävä7.png)

### Tehtävä 8
select name from goal w, goal_reached gr, game ga where gr.game_id = ga.id and gr.goal_id = w.id and ga.screen_name = "Heini";

![Tehtävä8](Images/Tentti3_Tehtävä8.png)

### Tehtävä 9
SELECT name FROM airport, game WHERE airport.ident = game.location AND game.screen_name = "Ilkka";

![Tehtävä9](Images/Tentti3_Tehtävä9.png)

### Tehtävä 10
SELECT country.name FROM airport, game, country WHERE airport.ident = game.location AND airport.iso_country = country.iso_country AND country.name = "United Kingdom" AND game.screen_name = "Ilkka";

![Tehtävä10](Images/Tentti3_Tehtävä10.png)

# Join harjoitukset

### Tehtävä 1
SELECT c.name as "country name", a.name AS "airport name" FROM country c INNER JOIN airport a ON c.iso_country = a.iso_country WHERE c.iso_country = "FI" AND a.scheduled_service = "yes";

![Tehtävä1](Images/Tentti4_Tehtävä1.png)

### Tehtävä 2
SELECT g.screen_name, a.name FROM game g INNER JOIN airport a ON g.location = a.ident;

![Tehtävä2](Images/Tentti4_Tehtävä2.png)

### Tehtävä 3
SELECT g.screen_name, c.name FROM game g INNER JOIN airport a ON g.location = a.ident INNER JOIN country c ON a.iso_country = c.iso_country;

![Tehtävä3](Images/Tentti4_Tehtävä3.png)

### Tehtävä4
SELECT a.name, g.screen_name FROM airport a LEFT JOIN game g ON a.ident = g.location WHERE a.name LIKE "%Hels%" ORDER BY g.screen_name DESC;

![Tehtävä4](Images/Tentti4_Tehtävä4.png)

### Tehtävä 5
SELECT go.name, ga.screen_name FROM goal go LEFT JOIN goal_reached gr ON go.id = gr.goal_id LEFT JOIN game ga ON ga.id = gr.game_id;

![Tehtävä5](Images/Tentti4_tehtävä5.png)

# Sisäkysely harjoitukset

### Tehtävä 1
SELECT name FROM country WHERE iso_country IN ( SELECT iso_country FROM airport WHERE name LIKE 'Satsuma%');

![Tehtävä1](Images/Tentti5_Tehtävä1.png)

### Tehtävä 2
SELECT name FROM airport WHERE iso_country in (SELECT iso_country FROM country WHERE name = "Monaco");

![Tehtävä2](Images/Tentti5_Tehtävä2.png)

### Tehtävä 3
SELECT screen_name FROM game WHERE id IN ( SELECT game_id FROM goal_reached WHERE goal_id = 7);

![Tehtävä3](Images/Tentti5_Tehtävä3.png)

### Tehtävä 4
SELECT name FROM country WHERE iso_country NOT IN (SELECT iso_country FROM airport);

![Tehtävä4](Images/Tentti5_Tehtävä4.png)

### Tehtävä 5
SELECT name FROM goal WHERE id NOT IN (SELECT goal_id FROM goal_reached WHERE game_id = 1);

![Tehtävä5](Images/Tentti5_Tehtävä5.png)
