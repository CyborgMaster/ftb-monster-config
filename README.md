ftb-monster-config
==================

Modifications for Minecraft FTB Monster config files to add gregtech and make it as hard as possible

command to generate diff file:
colordiff -rwNu 1.1.0-base 1.1.0-mod | less -R
diff -ru 1.1.0-base 1.1.0-mod > 1.1.0.patch

TODO:
- Update the base/patch file to include the new versions of the mods
- Document what mod versions have been updated
- Include here the extra mods to be downloaded and installed



Changes made directly to server configs without changing my config deploy:
B:"Allow RC steel to be used in other mods"=false

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
