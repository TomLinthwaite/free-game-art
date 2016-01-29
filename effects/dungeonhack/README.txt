-- DungeonHack 0.10                     --
-- http://dungeonhack.sourceforge.net   --


-- Welcome! --
Thanks for trying out DungeonHack!

This release features procedurally generated, foliage populated
terrain, along with one inn location and two dungeon locations. There
are monsters to fight and one quest to take that is managed by the Python
scripting system.

The codebase is not yet entirely mature, so be prepared to experience some
glitches and rough spots. Obviously the content and therefore the gameplay
is quite limited as well. However, there has been a lot of work going on under
the hood since the last release which will ensure a solid foundation as
DungeonHack is constantly being expanded and improved.


-- License --
Unless otherwise noted, source code and assets are licensed under
the terms of the GNU General Public License as published by the Free
Software Foundation; either version 3 of the License, or (at your option)
any later version.

Please see COPYING.txt for more details.


-- Starting off --
To start DH, run the appropriate script for your system (dungeonhack.bat
on Windows, dungeonhack on Linux). If the game does not run, you may
need some additional dependencies or if you have downloaded a source
distribution, please read the file INSTALL.txt.

The alpha begins at an inn. There is a ruin off to the right,
and a graveyard directly behind the starting location. You can reach
each with a bit of walking. You can get a quest in the Inn, along with
a weapon. You can also find a weapon by exploring the dungeon locations.


-- DungeonHack needs you! --
DH is an open source project - If you're a programmer, modeler, scripter,
or writer we could use your help! Stop into our project forums at
http://dungeonhack.sf.net/forums/ to help out or follow along with
our progress.


-- Controls --
- Mouse Controls:

Movement:       Move camera
Left Click:     Attack

- Keyboard Controls:

W,S,A,D:        Movement
Space Bar:      Use / Interact
Left Shift:     Hold to Run
E:              Jump
R:              Cast Fireball Spell
F12:            Take a Screenshot


-- Configuration and Performance --
If you're running an older computer, you can turn off grass in the
config.xml file in the Release directory. Just change the line
<doGrass value = "1" />
to
<doGrass value = "0" />

There are a number of other configuration variables in here that can
also be used to improve performance. Namely the ones dealing with trees,
whose values can be decreased for better performance but lower visual
quality. We recommend decreasing all the values at the same time in large
increments.

On the other hand, if you are willing to accept a slight drop in framerate,
we have an experimental bloom feature which can be enabled, and it is also
possible to increase the setting for the trees.


-- Bugs --
We would appreciate reports of any and all bugs. Before reporting a bug,
please check our tracker[1] and search the forums[2] to see if it has
already been reported. If not, please start a new topic on our forums,
giving as much information as possible such as operating system,
DungeonHack version, graphics hardware, and rendering mode (under
Windows). Please included a detailed description of what happened to
cause the bug.

[1] http://sourceforge.net/apps/trac/dungeonhack/report/3
[2] http://dungeonhack.sourceforge.net/forums/

Here's a list of known bugs associated with this release:
* Grass doesn't appear on terrain cells other than the current one
* The spider has no attack animation
* Fires never burn out and do no damage beyond initial explosion
* A tile will contain no more than 443 trees (about half the normal
  amount) on the Windows build due to an intermittent crash bug. If you
  do experience this bug despite the limitation, we would like to hear
  about it.


-- Closing Thanks --
Everyone who has contributed to the project or supported it over the
years.

Please see CREDITS.txt for more details on the individuals and
technologies involved in this project.

