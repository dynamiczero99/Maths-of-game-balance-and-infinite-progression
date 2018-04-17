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

Determinism refers to which kind of results can we expect from each move in the game. A _deterministic_ game would be one where any possible move always has the same result, there is not any kind of randomness involved on its execution, like Chess or Space Invaders, where enemies follow always the same pattern. On the other hand, _non-deterministic_ games will be affected by a roll of a random number in order to determine a result. Examples of non-deterministic games would be Parchís, where every move you do is affected by a dice roll, or Pokémon, which has many mechanics that rely on chances (an electric move with a 30% chance of paralyzing, an attack with a 15% critical hit chance...). A fast way to check if a game is or not deterministic is to check if, by having the game in its initial state, and being told every move that has been made in a match, you can recreate the exact same game state that match is right now. When that happens, a game is entirely deterministic.

### Transitive and intransitive games

A game's transitivity is determined by the "value" each possible option has. In math, intransitivity refers to The game is intransitive if all of the options are equally valuable, that is, that they have all the same chance of winning. In Rock, Paper, Scissors, we can calculate if the game is intransitive by computing the amount of possible outcomes that each move has. Rock can tie against rock (0), win againts scissors (+1) or lose against paper (-1). By adding 0+1-1 we get 0. The same goes for paper and scissors. The value of each option is exactly the same, so we can say that the game is intransitive.

### Solution

The solution of a game is the best action that can be taken in order to win it. This is only possible in deterministic games. In videogames, having a solution for our game is usually a non-desired trait, because it creates a big imbalance: players who know the solution will always win, and if both players know it, the game will either tie or be decided on who had the first move. Checkers is a game where this happens many times. You may find that in order to have a game of checkers result in the most optimal outcome for you, there are moves that should be avoided whilst other moves should be prioritised. What these moves are depends on the current arrangement of the checkers on the board, so it's not the solution of the game, but the solution to that game state. Checkers, as Go or Chess, have _theoretical complete solvability_, which means that they could eventually be solved but the number of possible permutations makes it impossible to calculate, by humans nor by current-day computers (or even the ones in near future, at the current exponential growth of computer power).

### Randomness

The term of randomness is really deep and has many subjects to study and take into account, but I will explain what is most useful to us as designers. The element of randomness comes from when board games were adapted into videogames, and they have been kept as a powerful tool that we can use to modify our games' system.

#### Gaussian Bells and how to handle randomness

A Gaussian Bell, or a Gaussian function, is a mathematical function that represents the amount of time a result has happened, and has a bell curve shape. What this function shows is that by having a random or pseudorandom system, we can predict the results that are going to happen more times. While the first results may seem completely random, eventually we will see that the values tend to group around a center. For a simpler explanation, if we throw a 6 faced dice enough times, we will get more 3s and 4s that any other number. This is because the larger the number of rolls, the more the average of results will tend to the average of possible values. So, if we want to treat a random value in our game as a determined one, we can make the arithmetic average of all the possible values (or just the lower and upper one if we are working with a number interval), and use that value instead. If a player can earn between 6 and 10 HP when leveling up, we will treat that value as 8. If the random element is an event that is bound to happen randomly, such as a critical hit, we can assume that the probability is the amount of times it will happen. For a 25% crit chance, we will count 1 attack from every 4 as a crit.

## How to balance a game

Game balance is a really complex topic. Usually when we balance a game we try to aim for a middleground between easy, which makes the game boring, or unforgiving, which makes it frustrating. But in that middleground there are many possible ways to go. The mindset that designers will have when balancing a game will depend on diverse factors:

- Setting/feel: Depending on the setting, you may aim for realistic or surrealistic approaches to movement. For example, a game set in World War II will have the player jump like a regular human would, but if you establish your player in, say, outer space, you may want to have a different gravitational force, changing the height and speed of the jump. The feel also takes part in this, because you may have characters that are set in a space where "regular physics" would apply, but for gameplay reasons you modify them so that they end up being less realistic. A good example for this is the difference in mechanics between Fortnite and PUBG.

<img src="/CheeryOrnateBellfrog-size_restricted.gif" alt="hi" class="inline"/>

Fighting Games and RTS Games usually are not that affected by this, because the gameplay needs characters to jump, move or attack in very strange and surrealistic ways.

- Target audience: When balancing your game, you will have to take into account what your playerbase will be. Thus, you can set the game's numbers to better fit the experience you want for your players. There are a lot of ways to do this, and we will delve deeper into this later. 

- Fairness: It should go without saying that difficulty is the easiest thing to create for a game, but what is truly challenging is to create a good and fair difficulty. The typical terms "you suck at this game" or "git gud" should never be on the designer's mouth when adressing players/testers. The game has to feel good and nice to play. This does not mean to make a game easy, because that can lead to boredom and eventually to your player to stop playing the game. What designers should aim for is to entertain, not to set up impossible challenges so that the game is tagged as "difficult".

### Luck vs Skill

Compare Chess to Parchís. One is purely deterministic, and the other is completely non-deterministic. Chess relies entirely on player skill, so a better player will almost always win, there is not any "luck" component that can lead him to lose. Parchís is a game where players never take any decision, they just roll a dice and move forward. So, we can say that luck makes a game more casual and less skill-based. In board games, this is not a problem, there are many games that rely only on luck and are pretty popular, and this can happen in videogames, but making this kind of a game usually ends up with a game to play for a while and then move on to something else, which is not what we want.

In order to raise the amount of skill required to win in a game, we can substract randomness, and do the opposite to lower it. This varies depending on your target, but most times if you're aiming for competitive, more serious kinds of games, you will need to reduce or nearly eliminate any random element of the game, and if you aim for a game that can be played by new players so that they can sometimes beat veteran ones, luck may be increased. But then again, there are competitive games that rely on luck, and if players are ok with that, there is no problem there.

### Dominant strategies

Something that you should avoid in your game is to have a "dominant strategy", a "best move". For instance, you can have 2 items on a game, one gives you +30 max health, and the other one +30 resistance. If we know that the formula for damage is, say: damage = attack - 0.7 x resistance, we can calculate how much of that resistance fares as "effective" health. In the end, that's what it is, resistance keeps you from being harmed, therefore it's like having more health. For each attack, the damage will be reduced by 21 points, so if the character is attacked twice, your deffense will mitigate 42 damage points. In only two attacks, the better resistance has already given us more effective health than the +30 health item. So, we can confirm that the +30 resistance item is considerably better than the +30 health one, therefore it's the dominant strategy, its the "solution" of this part of the game.

This hurts the gameplay so much because, first of all, a player that knows this will always have an advantage over a newcomer or just someone who doesn't know that, but also making an item much better than the other makes the last one essentially useless, and why would you want to give an option to players if one is clearly better and eventually no one will pick the weaker one? The only case where this can be used is when you want the players to solve a certain part of the game to advance forward or get some loot, for example. You can award them for taking the better choice, as if it was a puzzle.

Now, having dominant strategies is something that is bound to happen, and really hard to avoid if your game system is complex and elaborated. This is why multiplayer games keep releasing patches constantly to balance the game: they tend to have really deep and/or extensive game systems, and checking every possible combination in order to find what could possibly be a dominant strategy would be time consuming. The way to adress this problem is by testing and/or getting feedback from players, or maybe just simply watch them play. In your fighting game, is there any move that players tend to spam, and feels really powerful? Think of a countermeasure to that attack, maybe it can be blocked and its recovery is so long that you can get attacked first, or maybe there is a special move that can counter it. Then, maybe that special move is what gets spammed, so think of a countermeasure to that, too. Eventually, you will have a system with intransitive mechanics: all of the movements have the same (or a really similar) value, because each one has balanced strengths and weaknesses.

----------
