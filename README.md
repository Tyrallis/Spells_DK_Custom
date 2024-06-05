# Spells_DK_Custom
1. Put this module inside your build sources 'modules' folder (my case is F:\Source\modules)
2. once the module is inside your modules folder, open cmake and press "Configure". At the top should appear a new line in red called "SPELL_DK_CUSTOM", click configure once again so it turns white. 
3. Click Generate.
4. Open your Visual Studio and try to compile.
- IF Linker issues go inside VS -> Source Files -> ModulesLoader.cpp and inside there under "// Includes list" you put this 'void Addcustom_dkScripts();' and under "// Modules" you put this 'Addcustom_dkScripts();'
5.try to compile again. It should work.
6. Open Stoneharrys Spell Editor and go to ID 49560, right-click -> dublicate -> confirm.
7. You can change your Spell Description or Spell Name if you want to.
8. In "Base" Tab you change the Spell Visual 1 (Column 3, Row 2, Line1) to "10906".
9. In "Effects" Tab you go to "Spell Effects 1" and change Target B from "0 - Target_UNIT_NONE" to "15 - TARGET_UNIT_SRC_AREA_ENEMY".
10. Change Radius to 30 - 30 (since it's declared inside our spell script)
11. Save -> Export
12. copy the exported .dbc filed to your servers dbc folder (usually "Server\data\dbc") AND to you clients MPQ Patch
13.go inside your Database editor of your Choice, mine is HeidiSQL. From there you go into acore_world -> spell_script_names and scroll to spell_id 49560.
14. Dublicate that entry and edit the spell_id to the ID of your *probably* custom spell. Mine is 81015.
15. change the ScriptName to "spell_dk_death_grasp". 
16. Save

17. Start the server and pray nothing broke (i'm serious)
18. if no Database Errors, or non-existing spells inside Spell.dbc then great!
19. Go into your game and do .lookup spell "YOUR_SPELL_NAME
20. if it exists, it will show up, if it does, do ".learn "YOUR SPELL ID".
21. cast ingame
22. profit
