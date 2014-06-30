ftb-monster-config
==================

Modifications for Minecraft FTB Monster config files to add gregtech and make it
as hard as possible

TODO:
--------------------------------------------------------------------------
* Fix GregTech unification targets
  * All gems to project red
* Upgrade to 1.1.2
* Add iridium to extractor recipie

To Remove:
--------------------------------------------------------------------------
* Diamond Dolly - crashes when trying to put down barrel
* Ability to make enderium with the induction smelter (then you need an
  upgraded blast furnace to get it)
* Essence seeds - or at least the way to get them from grass
* Rainbow trees - maybe (too many golden apples)

Commands to generate and apply diff file
--------------------------------------------------------------------------
``` bash
colordiff -ruNw 1.1.1-base 1.1.1-mod | less -R
diff -ruN 1.1.1-base 1.1.1-mod > 1.1.1.patch
patch -p1 --no-backup-if-mismatch < ../1.1.1.patch
```

Mods to Remove
---------------------------------------------------------------------------
* Magic Crops (have to do something)
* Portal Gun (maybe)
* Tinkers Construct (maybe)
* Bedrock tools (maybe)
* Wraith Nodes

Added Mods
---------------------------------------------------------------------------
* GregTech: 4.08s
* Advanced Solar Panel: Version: 3.4.7
* Gravitation Suite: v1.9.9a

Disabled Mods
---------------------------------------------------------------------------
* Compact Solars

Enabled Mods
---------------------------------------------------------------------------
* JourneyMap
* ThaumicTinkerer
* Rei's Minimap (used for waypoints)

Changes made directly to server configs without changing my config deploy
----------------------------------------------------------------------------
All integrated

Server Only Changes
----------------------------------------------------------------------------
* Changed to using MCPC+ instead of pure forge server
* Start.bat changed, perm memory increased to 256

Added Server Mods:
* Dynmap

Added Server Plugins:
* Tekkit Customizer
* World Guard
* World Edit
* Essentials
* PermissionsEx v1.20.4 (Last version to work with 1.6.4)
