# Unchained-Blades-Save-Editor Version 1.0

This save editor is written in java, and provided as an executable jar file.  
Instructions how to install java: [https://www.java.com/en/download/help/download_options.xml]  
This program is a Save Editor tool for Unchained Blades (3DS).  

## Main Philosophy
### Part 1
From the beginning of the project I was adamant about one thing.  This save editor would allow for 'illegal values.'  A careful balance was developed between the level of illegality and user friendliness.  For example, with over 600 in-game items it would be extremely frustrating to lookup in a hex table the value you wanted.  Second, even illegal values have limits. If a value is being stored as 2 bytes it cannot assume a value greater than 65,535.  Included below are some notes of caution for those who are adventurous editors.
### Part 2
The original idea of this project was for a simple script to add a feature not included in the original game:  New Game Plus.  That is, provided you had a save file of cleared game you could generate a new save file that would start from the very beginning yet retain all items/stats/followers/etc.  For this reason nearly every set of data contains an "import" and "export" button that will aid in such massive data transfer.

## Main Tab
![image1](https://github.com/RPGFAN128/Unchained-Blades-Save-Editor/blob/master/screens/1.png)  
Editing the maximum number of followers can cause problems at the following points of the game (and possibly others)  
(1)  Advancing from Chapter 1 to Chapter 2.  
(2)  Advancing from Chapter 2 to Chapter 3.  
(3)  Advancing from Chapter 3 to Chapter 4.  
(4)  When recruiting Fang's Dragon Lords.  
In all instances when follower data is copied it relies on the "max followers" value.  If this is larger than it is supposed to it begins overwriting values in the stored items addresses.  
Editing your location will only take effect if you are in a dungeon area. (i.e. not town)  

## Items
![image2](https://github.com/RPGFAN128/Unchained-Blades-Save-Editor/blob/master/screens/2.png)  
(Currently no known issues)  

## Maps
![image3](https://github.com/RPGFAN128/Unchained-Blades-Save-Editor/blob/master/screens/3.png)  
Included in this release is a custom tile set to avoid copyright issues.  

## Master
![image4](https://github.com/RPGFAN128/Unchained-Blades-Save-Editor/blob/master/screens/4.png)  
If you are interested in exporting masters from a cleared game and importing them into a Chapter 1 save file please note that Master order is actually different in Chapters 1,2, and 3.  As an example, suppose you export Masters from a cleared game and import them into chapter 3.  Lucius would in fact be Fang, and if you advanced to chapter 4 you would find that Niko is actually Lucius.  You will have to manually keep track of any exported Master data and import them accordingly.  (Note a future release may allow individual master export/imports instead of all 8 at the same time)  
Editing your level will not make your character that level, edit experience instead.  
It would seem editing Max HP/MP does not permanently change your Master's stats.  Please wait for a future version fix.  
Editing strength-speed will not change your in-game stats of attack/defense/etc. unless you gain a level.  

## Follower
![image5](https://github.com/RPGFAN128/Unchained-Blades-Save-Editor/blob/master/screens/5.png)  
The editor shows 4 equipped slots for each master as well as 104 slots of stored followers.  Keep in mind the safe maximum number of followers is 104 counting both equipped and unequipped.  See level/experience argument from Master tab.

## Quest
![image6](https://github.com/RPGFAN128/Unchained-Blades-Save-Editor/blob/master/screens/6.png)  
This section was added at the last minute.  As such this tab is the least user-friendly.  Any future versions of this tab will be drastically different.  Forcing active quests may not work correctly with quests that contain scenes.  Var1 values seem to change for some quests as you progress in said quest.  Var2 values seem to count the kills in kill quests.  

## Future Possibilities
Treasure Chest Tab.  Treasure chest binary switches seem to be in addresses B018-B027.  As an example the first treasure you are required to collect is bit 7 in B018.  
Locked Doors Tab.  These binary switches seem to be in addresses B07C-B08B.  As an example the locked door requiring the Trial Key to unlock is bit 5 in B07C.  
An advanced mode that allows you to edit any (known) value to whatever value you wish.  As an example: an item value not allowed in the combo box.  
Item Synthesis Proficiency. To be honest I completely forget about mixing items and leveling up your "proficency" during this play through as I was hacking every item I needed.  
