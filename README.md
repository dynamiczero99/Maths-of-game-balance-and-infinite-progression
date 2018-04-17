# Maths of game balance and infinite progression

I am [Joel Cabaco Pérez](https://www.linkedin.com/in/joel-cabaco-6074a8160/), student of the
[Bachelor’s Degree in
Video Games by UPC at CITM](https://www.citm.upc.edu/ing/estudis/graus-videojocs). This content is generated for the second year’s
subject Project 2, under supervision of lecturer
[Ricard Pillosu](https://es.linkedin.com/in/ricardpillosu).

In this web page I'm going to explain the concept of game balance and give information on the topic in order to make not only more enjoyable games, but also to make them adapt to our vision of the project and our game pillars.

## What is game balance?

Game balance is the process where developers modify the numbers of the system of the game in order to fit a specific purpose. When a game is perfectly balanced, all of the participants in the game have exactly the same resources at hand, and the game is equally fair. An example of a perfectly balanced game, which are called _symmetric games_, would be Pong, because if both players have the exact same level of skill, each of them will have equal chances of winning. Games like Chess may seem to be symmetric, but in fact they are not, because whoever goes first will have an advantage over the other player. A way to balance these games would be what Go does; adding a certain number of points (in most rules, between 5 and 7) to the player with the white stones. This is because through calculations that we will further see in this topic, the first move advantage of the player with black stones is usually equal to those 5 to 7 points.

## Common terms and concepts

When talking about game balance, we will be using some specific, technical terms to refer to game properties, and talk about complex subjects.

### Determinism

Determinism refers to which kind of results can we expect from each move in the game. A _deterministic_ game would be one where any possible move always has the same result, there is not any kind of randomness involved on its execution, like Chess or Space Invaders, where enemies follow always the same pattern. On the other hand, non-deterministic games will be affected by a roll of a random number in order to determine a result. Examples of non-deterministic games would be Parchís, where every move you do is affected by a dice roll, or Pokémon, which has many mechanics that rely on chances (an electric move with a 30% chance of paralyzing, an attack with a 15% critical hit chance...). A fast way to check if a game is or not deterministic is to check if, by having the game in its initial state, and being told every move that has been made in a match, you can recreate the exact same game state that match is right now. When that happens, a game is entirely deterministic.

### Transitive and intransitive games

A game's transitivity is determined by the "value" each possible option has. In math, intransitivity refers to The game is intransitive if all of the options are equally valuable, that is, that they have all the same chance of winning. In Rock, Paper, Scissors, we can calculate if the game is intransitive by computing the amount of possible outcomes that each move has. Rock can tie against rock (0), win againts scissors (+1) or lose against paper (-1). By adding 0+1-1 we get 0. The same goes for paper and scissors. The value of each option is exactly the same, so we can say that the game is intransitive.

### Solution

The solution of a game is the best action that can be taken in order to win it. This is only possible in deterministic games. In videogames, having a solution for our game is usually a non-desired trait, because it creates a big imbalance: players who know the solution will always win, and if both players know it, the game will either tie or be decided on who had the first move. Checkers is a game where this happens many times. You may find that in order to have a game of checkers result in the most optimal outcome for you, there are moves that should be avoided whilst other moves should be prioritised. What these moves are depends on the current arrangement of the checkers on the board, so it's not the solution of the game, but the solution to that game state. Checkers, as Go or Chess, have _theoretical complete solvability_, which means that they could eventually be solved but the number of possible permutations makes it impossible to calculate, by humans nor by current-day computers (or even the ones in near future, at the current exponential growth of computer power).

### Randomness

The term of randomness is really deep and has many subjects to study and take into account, but I will explain what is most useful to us as designers. The element of randomness comes from when board games were adapted into videogames, and they have been kept as a powerful tool that we can use to modify our games' system. 

## How to balance a game

Game balance is a really complex topic. Usually when we balance a game we try to aim for a middleground between easy, which makes the game boring, or unforgiving, which makes it frustrating. But in that middleground there are many possible ways to go. The mindset that designers will have when balancing a game will depend on diverse factors:

- Setting/feel: Depending on the setting, you may aim for realistic or surrealistic approaches to movement. For example, a game set in World War II will have the player jump like a regular human would, but if you establish your player in, say, outer space, you may want to have a different gravitational force, changing the height and speed of the jump. The feel also takes part in this, because you may have characters that are set in a space where "regular physics" would apply, but for gameplay reasons you modify them so that they end up being less realistic. A good example for this is the difference in mechanics between Fortnite and PUBG.



- Target audience: When balancing your game, you will have to take into account what your playerbase will be. Thus, you can set the game's numbers to better fit the experience you want for your players. There are a lot of ways to do this, and we will delve deeper into this later. 

- Fairness: It should go without saying that difficulty is the easiest thing to create for a game, but what is truly challenging is to create a good and fair difficulty. The typical terms "you suck at this game" or "git gud" should never be on the designer's mouth when adressing players/testers. The game has to feel good and nice to play. This does not mean to make a game easy, because that can lead to boredom and eventually to your player to stop playing the game. What designers should aim for is to entertain, not to set up impossible challenges so that the game is tagged as "difficult".

### Luck vs Skill



----------
