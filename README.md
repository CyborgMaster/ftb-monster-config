ftb-monster-config
==================

Modifications for Minecraft FTB Monster config files to add gregtech and make it
as hard as possible

TODO:
* Fix unification targets
* check the placed block item number for blastfurnace (might be different and
  why the world check isn't removing it)

Mods to Remove:
* Magic Crops (have to do something)
* Portal Gun (maybe)
* Tinkers Construct (maybe)
* Bedrock tools (maybe)
* Wraith Nodes

Commands to generate and apply diff file
--------------------------------------------------------------------------
``` bash
colordiff -ruNw 1.1.0-base 1.1.0-mod | less -R
diff -ruN 1.1.0-base 1.1.0-mod > 1.1.0.patch
patch -p1 < ../1.1.0.patch
```

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

Changes made directly to server configs without changing my config deploy
----------------------------------------------------------------------------
All merged in


Server Only Changes
----------------------------------------------------------------------------
* Changed to using MCPC+ instead of pure forge server
* Start.bat changed, perm memory increased to 256

TekkitCustomizer used to enforce banned items:
Fertalized Dirt, BlastFurnace, Lilypad
Bans:
    CraftingBanned: []
    OwnershipBanned:
    - 1722:*:Lillypad of Fertility:Way too OP when combined with magic crops
    - 2648:*:Fertalized Dirt:Too OP when combined with magic crops
    - 30872:45:RC Blast Furnace:Too easy to get steel, use GT Blast Furnace
    UsageBanned:
    - 27585:2:Divining Rod III:Makes mining trivial, undermining the server economy.
    - 27526:*:Philosopher's Stone:Bypasses anti-grief to change blocks in protected areas without permission.
    PlacementBanned: []
    WorldBanned:
    - 1722:*:Lillypad of Fertility:Way too OP when combined with magic crops
    - 2648:*:Fertalized Dirt:Too OP when combined with magic crops
    - 30872:45:RC Blast Furnace:Too easy to get steel, use GT Blast Furnace
