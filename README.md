ftb-monster-config
==================

Modifications for Minecraft FTB Monster config files to add gregtech and make it
as hard as possible

TODO:
--------------------------------------------------------------------------
* Fix GregTech unification targets

To Remove:
--------------------------------------------------------------------------
None

Commands to generate and apply diff file
--------------------------------------------------------------------------
``` bash
colordiff -ruNw 1.1.0-base 1.1.0-mod | less -R
diff -ruN 1.1.0-base 1.1.0-mod > 1.1.0.patch
patch -p1 < ../1.1.0.patch
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
All Merged

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
