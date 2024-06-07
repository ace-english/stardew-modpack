-------------------HOW TO USE THIS MOD-------------------------------------
---(CP) Farmer Seasonal - Outfits And Portraits
also known as
---Seasonal Farmer Looks - Farmer's Portrait and Fashion Sense Outfits combined

The mod interfaces with two distinct frameworks - Farmer Portraits and FashionSenseOutfits. As both work via Content Patcher, it's possible to combine them into a single mod. Nonetheless, they are two distinct halves that need to be set up separately. They can also be used separately - if, for example, you despise Fashion Sense and would rather change outfits in-game manually, but want the portraits to change automatically, or if you think the Farmer Portraits sound complicated and intimidating and the portrait creator doesn't match the variety in Fashion Sense anyway - you can simply disable the half you aren't using in config. (Or don't - the mod automatically detects whether the required frameworks are installed and will only attempt to utilize the one(s) installed).

This readme is divided into 5 separate portions:
---QUICK START--- for when you just want to start playing and all the outfit stuff sounds confusing
---FILE STRUCTURE--- which explains the files inside the mod folder and how you should work with them
---PORTRAITS--- which explains how to set up portrait files
---OUTFITS--- which explains how to set up Fashion Sense outfits
---CONFIG--- which outlines the shared config.


---QUICK START---
To start your game with a single portrait and no Fashion Sense features:

1) inside the /assets folder next to this file, create a folder with your farmer's name. (Not your farm name, your FARMER's name);
2) go to https://jazzybee.itch.io/, select the fem or masc version of the portrait maker, create the portrait you want and save at any resolution;
3) put it inside the folder you've just made, make sure it's named "portrait.png";
4) play!

You can figure out the config and add more features/portraits/outfits later at any time!


---FILE STRUCTURE---
Yes, you do need to know this.

The main mod folder (the root) contains the "assets" folder, the "content.json" and "manifest.json" code files, this "readme.txt" file that you're reading right now, and possibly the "config.json" file if you have already launched the game with this mod in it at least once.

- manifest.json: the only reason you should ever have to touch this file is if I messed up the version number when updating the mod and you need to edit the version number in it to make SMAPI / your mod manager shut up about an update being available when you've already installed it. To do this, open the file, find the line that says "Version: "(some number)" and make this number match the version number in the downloads section of the mod page (https://www.nexusmods.com/stardewvalley/mods/19503?tab=files);

- content.json: this is the file you might want to edit to add custom mining, desert ot bathing locations or custom festivals. The instructions for how to do this are all inside the file, and can be found by searching for "//add custom mining locations", "//add custom desert locations", "//add custom bathing locations" and "//custom festival code sample" respectively. There is no other file you need to modify to make these changes;

- readme.txt: the file you're reading right now. Hi!

The assets folder should contain the "_code" folder, the "background.png" file and two sample portrait folders: "SampleName" and "SampleTwo".

- _code: !!!theoretically there are no circumstances under which you will need to interact with this folder in any way whatsoever!!! But just in case you're an intrepid coder who wants to make a personal change, here's the quick rundown. You'll notice that there is the same trio of "setup", "festival" and "mining" repeated twice times. One is for the outfits and one is for the portraits. The "setup" files are the ones called directly from content.json, and contain most of the actual outfit switching code, which has the same structure in both branches - sequential changes in the order in which the outfits overwrite each other. The "festival" files are separate so I can make a layered "if" check for DayEvent, and yes, it didn't work otherwise. The "mining" files are separate just because the code there is a bit of a pain in the ass. Yes, inside each file the same code is repeated six times with different conditions when just three would do; it's for readability. If you want to make a change that isn't fixing a typo I made, you'll have to make it at least twice, for the portraits and the oufits. Good luck;

- background.png: this mod does literally nothing with this one except load it, feel free to replace this file or never turn it on in the Farmer Portraits settings in the first place. Honestly, I expect you to. It's just there to prevent errors;

- SampleName: this is a folder that contains example portraits. Theoretically you can start up the game, make a new save with the farmer named SampleName, change nothing in the config, and these portraits will be used. In practice you're supposed to make your own folder named your farmer's name and put your own portraits there, using the portrait names in the SampleName folder as reference. (Copying SampleName and doing "Save As" to replace each of the portraits is a quick, easy and relatively foolproof way of doing that). Upon making changes in the game's config you can rename the files to whatever you want, though note that all portrait files should still start with "portrait_" after renaming.

- SampleTwo: this is a folder serving as an example of a minimal setup, when you just have one portrait for all occasions. Just make a folder with your farmer's name, put a "portrait.png" file into it and you're done. You can add more portraits later at any time.

- add more folders for each of your farmers! You can use the same folder for multiple saves with the same farmer if they share a name, or you can make a new folder for each save if the farmer has a different name in each. As I explained in the SampleName folder description, you can copy it and use its file names for reference, or you can give your files custom names that follow the format of "portrait_" + the postfix you set up in the in-game config (see the ---CONFIG--- section, or just figure it out in-game) ("portrait_base", "portrait_summerRain", "portrait_eveningDress", etc.)
-- each portrait file must be a square .png file at any resolution. Transparency is supported, have fun & go nuts;
-- there MUST be a "portrait.png" file in each folder. It will be overridden by any other portraits you use and you might never see it in-game ever if you use the seasonal outfits feature, but it must be there, or the mod won't work. Just copy some other portrait under that name, or keep the sample portrait.png, or use a random slug photo, it doesn't matter. It just needs to definitely load to give the other portraits something to edit;
-- it doesn't matter what else is in these folders than the files the mod will be looking for. Put as many sketches/WIPs/alternatives under different names there as you want. But:
-- UPON UPDATING THE MOD THE CUSTOM PORTRAIT FOLDERS WILL LIKELY BE LOST. Always back up all the portraits before updating, or better yet, store them elsewhere in the first place and just copy them to the mod folder after every update.


---OUTFITS---
This mod works with the Fashion Sense framework (download it here: https://www.nexusmods.com/stardewvalley/mods/9969) and the supplementary framework FashionSenseOutfits (download it here: https://www.nexusmods.com/stardewvalley/mods/18384).

To use Fashion Sense in-game, you will need the Hand Mirror item: when starting a new game you can tick the "start with mirror" box on the farmer setup screen, and with an already existent game you can buy it at Pierre's (iirc 2000g). Left clicking while holding the Hand Mirror opens the Fashion Sense menu, which allows you to override any and all parts of your look with clothing items / accessories from your installed Fashion Sense content packs. Look for them here: https://www.nexusmods.com/stardewvalley/mods/categories/13/ and here: https://www.nexusmods.com/stardewvalley/mods/categories/4/, or go to the Fashion Sense mod page, open the "Requirements" section in the description and go through the "Required by" part of it. (Make sure the packs you're downloading are for Fashion Sense and not something like Get Glam, and that they work with the current version of the game. Some of the top is last updated in 2017)

The Fashion Sense menu includes a "dresser" button, which opens the wardrobe menu where you can save outfits. This is what you'll need for this mod to work.

Step by step:
1. Download the frameworks specified above, then download content packs with hairstyles/accessories/clothes you want.
2. Acquire the mirror in-game.
3. Create the outfits you want this mod to switch you between and save them under any names you want.
-- note that if you set up an accessory in one outfit and then change to a different one that doesn't have any accessories set up for it, the accessory will carry over. This is reasonable behavior for something like elf ears - set up a bunch of outfits without them, then the last outfit with them, and enjoy elf ears in all outfits - but not even remotely so for something like a raincoat. Make sure all your outfits have at least one accessory! Add a belt or heterochromia or something.
4. Close the FS menu and put away the hand mirror. You don't need to carry it in your inventory except to change the outfits you've just set up.
5. Open the mod config and go through the settings to set them up to use the outfits you created.
-- note that the config is global and not save-specific. If you want to switch between multiple saves with different wardrobes (wardrobes are save-specific by default, though there's a "share outfit" button), you'll need to either use the same outfit names in all of them (such as the default ones in the config) or change the config every time you load a different one.
6. If you want to also use portraits and haven't set them up yet, now's the time to go to the ---PORTRAITS--- section of this readme!
7. You can change the config and the outfits in the hand mirror any time you like!


---PORTRAITS---
First of all, to use the portraits feature, you need to have the framework mod "Farmer Portraits" installed. Here it is: https://www.nexusmods.com/stardewvalley/mods/20713. It's recommended to disable the sample pack: while it should not cause errors, it is redundant with this mod.

Second, neither this mod nor any other I know about nor the vanilla game will generate the portraits for you. (Well, the Farmer Portraits default setting has your sprite enlarged to fill the portrait box. I'm assuming if you want to use this mod, you want something more substantial than that. There is a portrait maker at https://jazzybee.itch.io that you can use for this: it allows you to save the portrait in the exact right size and matches the vanilla portrait art style reasonably well. It only has so many options and doesn't match the diversity that Fashion Sense content packs offer, so it might come down to you doing your own pixel art anyway, at least to edit the generated portraits. (That's what I do)
 
Anyway, here's the sequence of what you need to do:
1. Open the mod folder, enter the /assets folder, and either copy one of the sample portrait folders ("SampleName" and "SampleTwo") then rename it into your farmer's name, or just create a folder with your farmer's name. (You could also just rename one of the sample folders without copying, but given you might want to use them for reference later, it's not really recommended)
2. Put a file named "portrait.png" into it. You can use one of the sample portraits for this, or a portrait generated by the portrait maker I linked above, or a random slug photo; but to start with, it's probably best to actually put the portrait of your farmer that you want to use as a base / default there.
3. Add any other portraits you already have ready and want to use for your farmer, named in the "portrait_[something].png" format. You can use the naming scheme from the SampleName folder, or you can use any custom postfixes you want and set them up in config later. Note though that your custom postfixes will also be your Fashion Sense outfit names, so they can't be too long: anything longer than 18 symbols will just not fit on the wardrobe screen. Don't worry about adding all the portraits you want to use ever, you can add more at any time.
4. Launch the game!
5. Open the mod config menu, find (CP) Farmer Seasonal - Outfits And Portraits, and set the mod up to use the portraits you have / want to use when you want to use them. Note that missing portraits that the mod is trying to load (other than portrait.png which should always be there) don't cause errors, you're simply left with the next highest priority portrait. 
6. If you want to use the outfits half of the mod too and haven't gotten to them yet, now's the time to look at the ---OUTFITS--- section of this readme!
----if you end up with more FS outfits than portraits, you can simply copy the portrait file that matches closest and rename it into the FS outfit name. Nothing stopping you from having a folder with 10 identical portraits that differentiate by the color of the skirt set up in the FS half.
7. At any later time you can add more portraits and change the ones you have around, and since 1.6 they will load dynamically during the game after you change the outfit you're supposed to wear back and forth (for example, go to the mines then leave them).


---CONFIG---
(The in-game config in the Generic Mod Config Menu includes detailed descriptions that should be self-explanatory, but if for some reason you want to edit the config.json file directly instead of using GMCM, this explanation is here for you)
The config is long and rich, and divided into several sections: the unnamed main settings section at the top, then ***Pajama controls, ***Outfit names, ***Festival outfits, and finaly ***Seasonal variations.

!Note that the config is global for all saves. If you're loading a different save and the mod doesn't seem to be working, go through the config and make sure the settings are correct and the outfit names match the currently loaded save.

*Use mod outfits
Turns on the Fashion Sense half of the mod. On by default. Note that you can toggle this at any time, as long as the required framework mods (Fashion Sense and FashionSenseOutfits) are installed. Possible values are "true" and "false". Enabled by default.

*Use mod portraits
Same as above, the required framework mod being "Farmer Portraits".

*Seasonal outfits
The farmer will attempt to wear different oufits and load different portraits depending on the season. If disabled, a "base" portrait and outfit will be shown, portrait_png and "base" by default. To customize Fashion Sense outfit names for different seasons (for example, to use the same outfit in three seasons and a different one in winter), scroll down to the corresponding config options. Default is "spring", "summer", "fall", "winter". These are also the default portrait file name postfixes. This outfit will be overwritten by any other option below that's enabled: raincoat, pajamas, etc. Possible values are "true" and "false". Enabled by default.

*Raincoat enabled
Turns on the "raincoat" feature: a special outfit (the default portrait file name postfix and outfit name are "rain", can be customized further down the config) will be worn when it's raining or storming in Stardew Valley. Overwritten by any other enabled option below this one: pajamas, a festival, etc. Possible values are "true" and "false". Enabled by default.

*Seasonal raincoats
Switches from using a single raincoat for any season to season-specific raincoats. Disabled by default - by default, a single raincoat is used. Possible values are "true" and "false". Doesn't do anything if the raincoat option above is disabled. Default outfit names are "SpringRain", "SummerRain", "FallRain", "WinterRain", default file postfixes are "rain_spring", "rain_summer", "rain_fall", "rain_winter", outfit names can be customized further down in the config. Possible values are "true" and "false". Enabled by default.

*Festival outfits
Turns on the "festival outfits" feature: you can set up a single festive outfit to be worn when anything at all (that the game registers as DayEvent) is going on, and you can set up outfits for individual festivals. Default file postfix for each is its DayEvent value in the game, which for vanilla festivals is their full name, e.g. "dance of the moonlight jellies", "spirit's eve", etc. See default outfit names further below, where they can be customized. Custom festivals can be added in the code manually, in the content.json file: open it and search for "//custom festival code sample", then follow the instructions there. Possible values are "true" and "false". This outfit will be overwritten by any other option below that's enabled: mining, desert, pajamas, etc (so you can visit Sandy on an Ice Festival morning without swearing in your winter coat). Enabled by default.

*Mining outfit enabled
Turns on the "mining outfit" feature: a special outfit (the default portrait file name postfix and outfit name are "mining", can be customized further down the config) will be worn in the "dungeon" locations: the mine, the quarry cave, the Skull Cavern and the volcano. Custom dungeon locations can be added in the code manually, in the content.json file: open it and search for "//add custom mining locations". Downtown Zuzu, East Scarp and Cape Stardew locations should already be included, although mistakes are possible. Tell me in the comments on the mod page if something is wrong! (https://www.nexusmods.com/stardewvalley/mods/19503?tab=posts) Possible values are "true" and "false". Enabled by default.

*Mountain mining
Has the farmer wear the mining outfit also to the "mountain" location - the map with the quarry, the Adventurer's Guild and mine entrance, the mountain lake, Robin's house and Linus's tent. Does nothing if the mining outfit is disabled. Possible values are "true" and "false". Disabled by default.

*Seasonal mining outfit
Has the mining outfit vary by season. See the seasonal variations section below.

*Desert outfit enabled
Turns on the "desert outfit" feature: a special outfit (the default portrait file name postfix and outfit name are "desert", can be customized further down the config) will be worn in the Calico desert, including Sandy's shop and the casino. Custom desert locations can be added in the code manually, in the content.json file: open it and search for "//add custom desert locations". Downtown Zuzu, Walk to Desert Redux and Desert Afforestation Area locations should already be included, although mistakes are possible. Tell me in the comments on the mod page if something is wrong! (https://www.nexusmods.com/stardewvalley/mods/19503?tab=posts) Possible values are "true" and "false". Enabled by default.

*Island outfit enabled
Turns on the "island outfit" feature: a special outfit (the default portrait file name postfix and outfit name are "island", can be customized further down the config) will be worn on all Ginger Island maps (including custom ones, as long as the LocationContext is correct).

*Island raincoat option
Selects which raincoat you wear on the Ginger Island when it rains: you can hook it up with the regular raincoat or the seasonal raincoat, you can set its own raincoat (default outfit name "IslandRain" and default portrait file name postfix island_rain), or you can turn it off and run around in your regular island outfit (or your regular outfit period). Possible values are "None", "Regular raincoat", "Seasonal raincoat" and "Island raincoat". Disabled by default (the "None" option). Always does nothing if "Raincoat enabled" is deselected.


***Pajama controls config section
		
*Morning pajamas
Turns on the morning half of the "pajamas" feature: a special outfit (the default portrait file name postfix and outfit name are "pajamas", can be customized further down the config and for the portrait file name, after turning off the "legacy portrait file names" option) will be worn in the farmhouse and the island farmhouse in the morning upon waking up. Possible values are "true" and "false". Enabled by default.

!Note that due to some inconsistent behavior of the FashionSenseOutfits framework it's recommended to use both the morning pajamas and the evening pajamas feature: when loading a save, you will wake up in the same outfit you went to bed in, even when it would normally be switched on starting a new day if you were playing continuously, and it will not switch to what it should be until either time ticks over (6:10am) or you switch locations (leaving the farmhouse or going to the cellar). Going to bed and waking up in the same pajamas makes the issue fully invisible.

*Pajamas until
Sets when you change out of pajamas and into your outfit for the day when inside the farmhouse (leaving the farmhouse changes you out of pajamas regardless, but if you go back in and it's still pajamas time, you'll be wearing them again). It's a multi-select instead of free text entry because I have to correspond each option to in-game time manually, because json is not a real programming language. You understand. Possible values are "6:10", "6:20", "6:30", "7:00", "7:30", "8:00", "8:30", "9:00", "10:00", "11:00", "12:00". Default is "6:10". It's all in the AM, obviously, because it's about wearing pajamas in the morning.

*Evening pajamas
Turns on the evening half of the "pajamas" feature, see above. Has you wear pajamas in the farmhouse before you go to bed; together with morning pajamas constitutes an effective workaround to the FashionSenseOutfits save load issue. Possible values are "true" and "false". Enabled by default.

*Pajamas from
Sets when you change from your outfit for the day into pajamas when inside the farmhouse in the evening, same as "pajamas until" above in all respects, except time is first in PM and then in AM as we cross the midnight point. Possible values are "9:00", "9:30", "10:00", "10:30", "11:00", "11:30", "12:00", "12:30", "1:00", "1:30", "1:40", "1:50". Default is "10:00" (10 PM, obviously).

Note that the pajamas feature overrides all other outfit options: as long as you're in the farmhouse or the island farmhouse and it's the right time, you will be wearing pajamas regardless of the season, festival, whether you added your farmhouse as a mining or desert location for some reason, etc.

***Outfit names config section

!Note that the config is global for all saves. If you intend on switching between different saves with different wardrobes, you'll need to either use the same outfit names in all of them (such as the default ones), or change the settings every time you switch.

*Base outfit
For the outfit you wear day to day when you aren't wearing anything else, sets the name of the Fashion Sense outfit in your wardrobe as well as the portrait file name postfix. Only actually relevant when you're not using the seasonal outfits feature, since there's always SOME season and that's what you'll be wearing instead. Use example: entering "overalls" into this setting will have the mod load the "overalls", "Overalls", "OVERALLS" or however else you capitalize the outfit name from your Fashion Sense wardrobe, and "portrait_overalls.png" (or "pOrTrAiT_oVeRaLlS.png" or however else you capitalize it) from your portraits folder. Note that it will load "portrait.png" first in all cases and missing the "portrait_overalls.png" file will not cause an error, the previous portrait (directly portrait.png in this case) will be loaded instead. The default value is "base".

*Pajamas
For the outfit you wear in the morning and/or evening, if enabled, sets the name of the Fashion Sense outfit in your wardrobe as well as the portrait file name postfix. See *Base outfit for use example. The default value is "pajamas".

*Raincoat
For the outfit you wear when it's raining, if it's enabled and the seasonal raincoats option is disabled, sets the name of the Fashion Sense outfit in your wardrobe as well as the portrait file name postfix. See *Base outfit for use example. If the "island raincoat option" is set to "regular raincoat", it will use this outfit name even if you're wearing seasonal raincoats on the mainland. The default value is "rain".

*Mining outfit
For the outfit you wear while mining/dungeoneering, if enabled, sets the name of the Fashion Sense outfit in your wardrobe as well as the portrait file name postfix. See *Base outfit for use example. The default value is "mining".

*Desert outfit
For the outfit you wear in the Calico desert (and other desert locations if you have any in your game, see *Desert outfit enabled above for instructions on adding custom locations to the list), if enabled, sets the name of the Fashion Sense outfit in your wardrobe as well as the portrait file name postfix. See *Base outfit for use example. The default value is "desert".

*Island outfit
For the outfit you wear on Ginger Island, if enabled, sets the name of the Fashion Sense outfit in your wardrobe as well as the portrait file name postfix. See *Base outfit for use example. The default value is "island".

*Island raincoat
If you have selected the "Island raincoat" option in the corresponding setting, sets the name of the Fashion Sense outfit in your wardrobe as well as the portrait file name postfix, for the raincoat you wear when you're on the island and it's raining there. See *Base outfit for use example. The default value is "islandRain".
		
***Festival outfits

!Note that this entire section doesn't do anything if the "Festival outfits" option is disabled in the main config.

Note that all festival outfits are overwritten by more specific outfits: island, desert, mining, pajamas, etc. They will however overwrite the raincoat, if your modded game makes it possible for it to rain during a festival (not possible in the vanilla game), and of course they overwrite seasonal outfits.

*Single festive outfit
If this option is enabled, you will wear a "default" festive outfit for all occasions that have a DayEvent value in the game (vanilla festivals, weddings, anything added by mods). Disable it to default to your regular outfit on occasions you aren't interested in and won't set the value for below. Note that adding specific custom festivals to this mod's code is relatively easy: open the "content.json" file in the mod folder, search for "//custom festival code sample", then follow the instructions there. Of course, using this option is undoubtedly easier. Possible values are "true" and "false". Enabled by default.

*Festive outfit
For the outfit you'll wear on festive occasions by default, if enabled above, sets the name of the Fashion Sense outfit in your wardrobe, and if the "legacy file names" setting is off, also the portrait file name postfix. See *Base outfit for use example. The default value is "festive".
		
*Wedding outfit enabled
When enabled, makes you wear a special outfit on your wedding day. (Note that this is for the whole day, not just the ceremony; I don't think Content Patcher allows me to separate it out). If it's disabled, you will either wear the "default" festive outfit on your wedding day (if the corresponding option is enabled) or your regular seasonal / default outfit (if it isn't). Possible values are "true" and "false". Enabled by default.

*Wedding outfit
For the outfit you wear on the day of your wedding, if enabled above, sets the name of the Fashion Sense outfit in your wardrobe as well as the portrait file name postfix. See *Base outfit for use example. The default value is "wedding".
		
*Egg Festival outfit enabled
When enabled, makes you wear a special outfit on the day of the Egg Festival. If it's disabled, you will either wear the "default" festive outfit on that day (if the corresponding option is enabled) or your regular seasonal / default outfit (if it isn't). Possible values are "true" and "false". Enabled by default.

*Egg Festival outfit
For the outfit you wear on the day of the Egg Festival, if enabled above, sets the name of the Fashion Sense outfit in your wardrobe as well as the portrait file name postfix. See *Base outfit for use example. The default value is "EggFestival".
		
*Flower Dance outfit enabled
*Flower Dance outfit
Same as above, default is "FlowerDance".

*Luau outfit enabled
*Luau outfit
Same as above, default is "Luau".

*Dance of the Moonlight Jellies outfit enabled
*Dance of the Moonlight Jellies outfit
Same as above, default is "MoonlightJellies".

*Stardew Valley Fair outfit enabled
*Stardew Valley Fair outfit
Same as above, default is "Fair".
		
*Spirit's Eve outfit enabled
*Spirit's Eve outfit
Same as above, default is "SpiritsEve".

*Ice Festival outfit enabled
*Ice Festival outfit
Same as above, default is "IceFestival".

*Feast of the Winter Star outfit enabled
*Feast of the Winter Star outfit
Same as above, default is "WinterStar".

!Note: this is the part of the config where the custom festival setup will go if you add any. To do so, open the "content.json" file in the mod folder, search for "//custom festival code sample" and follow the instructions there.

***Seasonal variations config section

*Spring outfit
*Summer outfit
*Fall outfit
*Winter outfit
For the outfit you wear in the respective season when nothing else that overrides it is going on, sets the name of the Fashion Sense outfit in your wardrobe as well as the portrait file name postfix. See *Base outfit for use example. The default values are "Spring", "Summer", "Fall" and "Winter" respectively. Doesn't do anything if the "Seasonal outfits" option is disabled in the main settings section.

*Spring raincoat
*Summer raincoat
*Fall raincoat
*Winter raincoat
For the outfit you wear in the respective season when it rains, sets the name of the Fashion Sense outfit in your wardrobe as well as the portrait file name postfix. See *Base outfit for use example. The default values are "SpringRain", "SummerRain", "FallRain" and "WinterRain" respectively. Doesn't do anything if the main "raincoat enabled" setting is off, and also if you don't have seasonal raincoats enabled in the main settings section or chosen as an island raincoat option. (I have no idea why you would use seasonal raincoats for the island but a single raincoat for the mainland, but you could in fact do that)

*Spring mining outfit
*Summer mining outfit
*Fall mining outfit
*Winter mining outfit
For the outfit you wear while mining in the respective season, sets the name of the Fashion Sense outfit in your wardrobe as well as the portrait file name postfix. The default values are "SpringMining", "SummerMining", "FallMining" and "WinterMining" respectively. Doesn't do anything if the mining outfit is disabled, as well as if the seasonal mining outfits option is disabled.


Have fun playing Stardew Valley!
- your Liliet