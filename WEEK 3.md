# WEEK 3
## SIMPLE QUERY
## EXERCISE 2
# Q1:
select * from goal;
![Screenshot (1).png](Screenshot%20%281%29.png)

# Q2:
select name, type from airport where iso_country = "FI";
![Screenshot (2).png](Screenshot%20%282%29.png)

# Q3:
select name from airport where iso_country = "FI" order by name asc;
![Screenshot (3).png](Screenshot%20%283%29.png)

# Q4:
select name, type from airport where iso_country = "FI" order by type asc, name asc;
![Screenshot (4).png](Screenshot%20%284%29.png)

# Q5:
select name from country where name like "F%";
![Screenshot (5).png](Screenshot%20%285%29.png)

# Q6:
select name from country where name like "%F%";
![Screenshot (6).png](Screenshot%20%286%29.png)

# Q7:
select location from game where screen_name = "Vesa";
![Screenshot (7).png](Screenshot%20%287%29.png)

# Q8:
select co2_consumed from game where screen_name = "Ilkka";
![Screenshot (8).png](Screenshot%20%288%29.png)

# Q9:
select distinct co2_budget from game;
![Screenshot (9).png](Screenshot%20%289%29.png)

# Q10:
select screen_name, co2_budget, co2_consumed, (co2_budget-co2_consumed) as co2_lef 
from game where screen_name = "Ilkka";
![Screenshot (10).png](Screenshot%20%2810%29.png)

#EXERCISE 3: JOIN
# Q1:
select country.name as "country name", airport.name as "airport name"
from country, airport
where country.iso_country = airport.iso_country
and country.name = "Iceland";
![Screenshot (3.1).png](Screenshot%20%283.1%29.png)

# Q2:
select name from airport where type = large_airport;
![Screenshot (3.2).png](Screenshot%20%283.2%29.png)

# Q3:
select country.name as "country name", airport.name as "airport name"
from country, airport
where country.iso_country = airport.iso_country
and country.name = "Antarctica";
![Screenshot (3.3).png](Screenshot%20%283.3%29.png)

# Q4:
select airport.elevation_ft
from game, airport
where game.location = airport.ident
and game.screen_name = "heini";
![Screenshot (3.4).png](Screenshot%20%283.4%29.png)

# Q5:
select (airport.elevation_ft * 0.3048) as elevation_m
from game, airport
where game.location = airport.ident
and game.screen_name = "heini";
![Screenshot (3.5).png](Screenshot%20%283.5%29.png)

# Q6:
select airport.name
from game, airport
where game.location = airport.ident
and game.screen_name = "Ilkka";
![Screenshot (3.6).png](Screenshot%20%283.6%29.png)

# Q7:
select country.name
from game, airport, country
where game.location = airport.ident and country.iso_country = airport.iso_country
and game.screen_name = "Ilkka";
![Screenshot (3.7).png](Screenshot%20%283.7%29.png)

# Q8:
select goal.name
from game, goal, goal_reached
where goal_reached.goal_id = goal.id and goal_reached.game_id = game.id
and game.screen_name = "heini";
![Screenshot (3.8).png](Screenshot%20%283.8%29.png)

# Q9:
select airport.name
from game, goal, goal_reached, airport
where goal_reached.goal_id = goal.id and goal_reached.game_id = game.id and game.location = airport.ident
and game.screen_name = "Ilkka";
![Screenshot (3.9).png](Screenshot%20%283.9%29.png)

# Q10:
select country.name
from game, goal, goal_reached, airport, country
where goal_reached.goal_id = goal.id and goal_reached.game_id = game.id
and game.location = airport.ident and country.iso_country = airport.iso_country
and game.screen_name = "Ilkka";
![Screenshot (3.10).png](Screenshot%20%283.10%29.png)








