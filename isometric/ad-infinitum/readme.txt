Ad-Infinitum

##################################################################

http://sourceforge.net/projects/ad-infinitum/

email:  tristanmcduff@yahoo.com

##################################################################

execute notes

v. 1.9.9.1.4

needs windows and direct X, but should run on most versions of both these.

has also been reported to run in: Wine (on Ubuntu Linux 7.04 )

##################################################################

this version is testing the unites, the unites are two types:"nobles" and basic "infantry", 
factions are also introduced (diferent coloured units on some worlds, 
e.g the yellow labeled world named "Angel" or the orange "Yonder".) 
Units can be found on planets standing on palaces (Nobles), forts or towns where these are located.
he town selection of the previous versions has been turned back on but the town
icon selection and manipulation however has been turned off, the code for icon selection and 
manipulation has become unstable with the new zoom features and needs further debuging.

Verious ajustments to the mouse click on unit or town to make more user friendly. 
added a mimi unit icon to indicate unit selection. Note that the mouse prety much operates on 
the princile: left click selects, right click deselects or exits from where you are or what you are doing.
I hope this simple interface will make things easier to manipulate.

I attempted a routine to graduly zoom out over 1 to 2 seconds to a x2 view when a unit is selected. 
This code however has problems and needs further work. Accordingly turned off for the moment.

Test of factions. A few diferent faction units have been placed on some worlds (e.g. Yonder or Angel).
moving these inits into each other creats a "conflict", this is just a "stand off" at the moment. 
movement of units now also includes information on units facing direction.

test of ai and game speed. the planet CAPITAL has been given a large number of units to play with.
these units will randomly wait a varied time spane and move to random specific locations 
(i.e. randomly move to the closest factory, or the closest mine, or the closest lab....ect) 
these movements hapen while the game is in play and are there to test the speed of the ai  
pathfinding in relation to the rest of the game.

note that the pause at the start of the game is the "universe generating". 
the idea is that every time the game is played the universe is totaly diferent, 
hence must be generated from scratch, restart game or press f4 during game to see a new creation

####################################################################

I have turned off the debuger as this was writting information that is only useful 
to myself. I have reduced the number of worlds to 75. this is much faster and 
suficient at this stage to get a feelfor the game if you want to see the game with more words, 
change "Num_Star: 75" in the input.txt file in the debug folder to "Num_Star: 250". 

###################################################################

the screen size will now be set automaticaly from the size used at desktop

##################################################################

it should now be possible to run the game with 16 bits graphics.
the default is 32 bits. to change this, set in the input.txt file
the line:

bits_color: 32

may be changed to:-

bits_color: 16

or (not tested):- 

bits_color: 24 (unstable)

##################################################################

program is not yet playable 
but gives a sence of things to come

##################################################################

to run: adinfinitum.exe
-
esc .....exits program at any stage
f1 f2....uses a test zoom feature on world maps
f3 f4 etc regenerates universe
-
Basicaly: left click in the game selects what the cursor in on, and right click deselects.
-
on space map:
right click drag - scrolles map
left click on world selects world and enters orbital world's map
-
clicking on maps of worlds has various results:
Bsicaly: left click zooms in and selects, right click zooms out if nothing is selected, 
otherwise it deselects. 
left click on a unit selects, then left click where you want 
unit to walk to. right click deselects unit
left click on a structure selects the structures "town" group and displays where 
the population is working in the form of icons with there doubles linked to industry or farming.
There are 3 population icons per houses hex, white icon is "unemployed". 
note that the factories only have smoke if population is working in them, otherwise they are abandoned.
-
to exit world map:
Right click to deselect what you are doing (e.g. moving unit), right click again to to to orbit view,
and from orbit view, right click againe to go to space map.
SPACE bar.
-
Zoom: 
mouse wheel has been turned off as the code does not seem conpatible with my 
new compiler, will see what is happening here at a later stage.
f1 f2....uses the test zoom feature on world maps (has odd results at this stage)


##################################################################

note: i need help on the graphics

##################################################################

end