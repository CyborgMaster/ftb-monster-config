ftb-monster-config
==================

Modifications for Minecraft FTB Monster config files to add gregtech and make it
as hard as possible

Commands to generate and apply diff file
--------------------------------------------------------------------------
colordiff -rwNu 1.1.0-base 1.1.0-mod | less -R
diff -ru 1.1.0-base 1.1.0-mod > 1.1.0.patch
patch -p1 < ../1.1.0.patch

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

Changes made directly to server configs without changing my config deploy
----------------------------------------------------------------------------
Removed most of the recipies for the Advanced Solar Panels Molecular
Transformer, only left the sunarium part recipie

OpenBlocks elevator drains exp = true


B:"Allow RC steel to be used in other mods"=false

Removed the easy thermal expansion recipies for ModularPowersuits:
* \config\machinemuse\recipes\ThermalExpansion.recipes

Added directly to minetweaker/main.cfg:
# Remove Lilypad of Fertility (too OP when combined with sprinklers)
# minetweaker.remove(tile.lilypad);
minetweaker.remove(<1722>);

# Remove Fertalized Dirt, also too OP for growing plants
minetweaker.remove(<2648>);

# Remove crafting recipie for RotaryCraft blast furnace (Too cheap to get steel, use GT Steel)
# rcBlastFurnace = item.machineplacer."45";
minetweaker.remove(<30872:45>);

# Add recipe to convert GregTech steel to RotaryCraft steel
# gtSteel = item.GT_Materials."26";
# rcSteel = item.shaftcraft.crafting.ingot;
# recipes.addShaped(rcSteel * 4, [[gtSteel, gtSteel], [gtSteel, gtSteel]]);
recipes.addShaped(<30887:1> * 4, [[<9630:26>, <9630:26>], [<9630:26>, <9630:26>]]);

Changed to using MCPC+ instead of pure forge server. Start.bat changed, perm sized upped to 256:
"C:\Program Files\Java\jre7\bin\java.exe" -Xms3G -Xmx3G -XX:PermSize=256m -jar mcpc-plus-1.6.4-R2.1-forge965-B251.jar nogui

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
