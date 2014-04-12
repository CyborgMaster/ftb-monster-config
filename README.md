ftb-monster-config
==================

Modifications for Minecraft FTB Monster config files to add gregtech and make it as hard as possible

command to generate diff file:
colordiff -rwNu 1.1.0-base 1.1.0-mod | less -R
diff -ru 1.1.0-base 1.1.0-mod > 1.1.0.patch

TODO:
- Update the base/patch file to include the new versions of the mods
- Document what mod versions have been updated
- Disable RotaryCraft steel with config instead of minetweaker script
- Include here the extra mods to be downloaded and installed

Changes made directly to server configs without changing my config deploy:
B:"Allow RC steel to be used in other mods"=false
