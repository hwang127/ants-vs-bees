# ants-vs-bees

In this project, I implemented a tower defense game called Ants Vs. SomeBees. As the ant queen, you populate your colony with the bravest ants you can muster. Your ants must protect their queen from the evil bees that invade your territory. Irritate the bees enough by throwing leaves at them, and they will be vanquished. Fail to pester the airborne intruders adequately, and your queen will succumb to the bees' wrath. This game is inspired by PopCap Games' Plants Vs. Zombies.

A game of Ants Vs. SomeBees consists of a series of turns. In each turn, new bees may enter the ant colony. Then, new ants are placed to defend their colony. Finally, all insects (ants, then bees) take individual actions. Bees either try to move toward the end of the tunnel or sting ants in their way. Ants perform a different action depending on their type, such as collecting more food, or throwing leaves at the bees. The game ends either when a bee reaches the ant queen (you lose), or the entire bee fleet has been vanquished (you win).



ants.py: The game logic of Ants Vs. SomeBees

ants_gui.py: The original GUI for Ants Vs. SomeBees

gui.py: A new GUI for Ants Vs. SomeBees

graphics.py: Utilities for displaying simple two-dimensional animations

state.py: Abstraction for gamestate for gui.py

utils.py: Some functions to facilitate the game interface

assets: A directory of images and files used by gui.py

img: A directory of images used by ants_gui.py

ok: The autograder

proj3.ok: The ok configuration file

tests: A directory of tests used by ok

mytests.rst: A space for you to add your custom tests; see section on adding your own tests

***Core concepts***


The Colony. This is where the game takes place. The colony consists of several places that are chained together to form a tunnel where bees can travel through. The colony has some quantity of food that can be expended to deploy ant troops.

Places. A place links to another place to form a tunnel. The player can place a single ant into each place. However, there can be many bees in a single place.

The Hive. This is the place where bees originate. Bees exit the hive to enter the ant colony.

Ants. Ants are the usable troops in the game that the player places into the colony. Each type of ant takes a different action and requires a different amount of food to place. The two most basic ant types are the HarvesterAnt, which adds one food to the colony during each turn, and the ThrowerAnt, which throws a leaf at a bee each turn. You will be implementing many more.

Bees. Bees are the antagonistic troops in the game that the player must defend the colony from. Each turn, a bee either advances to the next place in the tunnel if no ant is in its way, or it stings the ant in its way. Bees win when at least one bee reaches the end of a tunnel.

Queen Ant: There is one queen ant in the whole colony. She is able to attack bees but she also has a special ability of fortifying the other ant troops. Bees can also win if they destroy the queen ant.

***Playing the game***

The game can be run in two modes: as a text-based game or using a graphical user interface (GUI). The game logic is the same in either case, but the GUI enforces a turn time limit that makes playing the game more exciting. The text-based interface is provided for debugging and development.

The files are separated according to these two modes. ants.py knows nothing of graphics or turn time limits.

To start a text-based game, run


python3 ants.py

To start a graphical game, run

python3 gui.py
