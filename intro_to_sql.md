1. Find all the robots from Star Wars
    select * from robots where source like 'Star Wars';
    C3P0
    R2D2

2. Find the robot with an "anxious" personality
    select * from robots where personality = 'anxious';
    C3P0

3. Find all recipes that are nut free.
    select name from recipes where nut_free=true;
    
    Butternut Squash Bake
    Vegetarian Bibimbap
    French Veggie Loaf
    Quinoa and Black Beans
    Juicy Roasted Chicken
    Garlic Green Beans
    Stout Slow Cooker Corned Beef and Veggies

4. Count the number of recipes that are gluten free but not vegetarian
    select count(*) from recipes where gluten_free=true AND vegetarian=false;

    2

5. Find the animal with the most legs.
    select max(number_of_legs) from animals; 
        8
    select * from animals where number_of_legs=8;
        octopus

6. Find the board game that takes the least amount of time to play.
    select * from board_games where mins_to_play = (select min(mins_to_play) from board_games);

        Sushi Go 15 mins
        Quixo 15 mins
    
7. Find the recipe that takes the most time to prepare.
    select name,minutes_required from recipes where minutes_required=(select max(minutes_required) from recipes);

        Stout Slow Cooker Corned Beef and Veggies 390 minutes

8. Find all the robots whose name starts with the letter M.

    select name from robots where name like 'M%';

        Marvin
        Mr. Butlertron

9. Count the number of board games that can be played by 8 people.

    select count(*) from board_games where max_players >=8;

        3

10. Find all animals that are swimming and egg-laying.
    
    select name from animals where swimming=true and egg_laying=true;

        octopus
        duck

11. Find all animals that are swimming and egg-laying but not flying.

    select name from animals where swimming=true and egg_laying=true and flying=false;

        octopus
    
12. Find the board game that supports the largest number of people.

    select name,max_players from board_games where max_players = (select max(max_players) from board_games);

        Cards against Humanity 30 players
