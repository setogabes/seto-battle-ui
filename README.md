Disclaimer: I'm an artist, not a developer. All design choices, custom assets and ideas present in this mod are my own, but the code itself was written by chatGPT and Gemini. No generative AI was used in the making of assets.

Also, this is my first mod. So if anything is out of place or wrong, please let me know!

This is my mod, Seto Battle UI.
A different take on the classic battle HUD that aims to be fully customizable, even for people who have no experience with coding whatsoever. I couldn't find any mod for the battle UI that satisfied me 100%, so I tried to create my own.

It's based around the layouts from the first few pokémon gens, and it features:

- EXP bar
- Indicator stating if the pokémon you're currently battling was already caught
- Move description
- Different move colors according to it's type
- Reworked menus (FIGHT, ITEMS, PKMN)
- Usable items separated from the rest inside of the bag
- Adjustable toggles for scale, font size, and font color
- Theme support

I'm a sucker for customization. So theme support was something that I REALLY wanted to implement here. The mod currently comes with two themes:

DEFAULT:
It's just the barebones UI created by code. Originally it was there just as a placeholder to test layout decisions and put everything where I wanted to be, but now it works as a default theme that follows the black and white simple gen 1 visuals. It also acts as a fallback in case some custom theme's asset fails to load.

HGSS:
Created by me, inspired by the Heartgold/Soulsilver DS games.

-

Wanna make your own theme? All you need is an image editor, and a file explorer!

Inside the mod there's an "assets/custom_ui" folder. Every folder inside custom_ui will be treated by the game as a new theme, that you can apply in game by going to the mod's options.

Inside your theme's folder, all you need to do is paste your own assets to be read by the game. They must be png files named in specific ways that allows the mod to put them where they each need to be. Here's a quick summary of what's what, with a general size recommendation, if you want to build your own:

Top UI:
enemy_top_bg.png: Enemy pokemon's info (Name, HP, etc)
player_top_bg.png: Your pokemon's info (Name, HP, etc)

Each of those files are 97x34 pixels in size.

-

Bottom UI:
message_bg.png: The rectangle in the bottom of the screen that shows text saying what's going on (296x48 in size)

main_menu_bg.png: Rectangle at the bottom with FIGHT, ITEMS, PKMN and RUN buttons (296x48 in size) 

moves_left_bg.png: Under the FIGHT menu, the rectangle at the bottom left that shows your pokémon's moves (184x48 in size)

moves_right_bg.png: Under the FIGHT menu, the rectangle at the bottom right that shows the highlighted move description, type and PP amount (104x48 in size)

-

Other windows and menus:
bag_bg.png: The window that opens when you select the ITEMS option (272x112 in size)

party_bg.png: The window that opens when you select the PKMN option (272x112 in size)

party_slot_bg.png: The rectangle that encapsulates each pokemon sprite and info inside your party window (112x25 in size)

summary_bg.png: the window that shows your pokemon information when you click to see it's stats inside the party window (272x112 in size) 

-

Icons:
btn_fight.png: Image that acts as a button for the FIGHT option in the menu
btn_item.png: Image that acts as a button for the ITEMS option in the menu 
btn_pkmn.png: Image that acts as a button for the PKMN option in the menu 
btn_run.png: Image that acts as a button for the RUN option in the menu

All of them are 62x50 pixels in size.

-

Move types:
(These are auto explanatory, but yeah, each file here will serve as a background for a pokemon move, depending on the move's type)
type_normal.png
type_fire.png
type_water.png
type_grass.png
type_electric.png
type_ice.png
type_fighting.png
type_poison.png
type_ground.png
type_flying.png
type_psychic.png
type_bug.png
type_rock.png
type_ghost.png
type_dragon.png
type_dark.png
type_steel.png
type_fairy.png

All of them are 63x13 pixels in size
 
-

If you create a cool theme, please post some screenshots here, and maybe consider sharing it as well! The whole point of all this is making theme support a community thing!

-

Notes:

- Compatible with PotatoVoxel, BattleArt, Dramatic, Ascendant and Dramaless voxels. It should automacially appear instead of any other mod's battle UI tho.

- This mod forces battle layout to "OG" to lock the pokemon sprites at the center of the screen. The UI can be toggled to stay at the center or the sides by selecting "Wide Top UI" on or off on options.

- Transparency in the assets' png works in game

- The sizes mentioned here are recommendations instead of specific limits. You can play around with your assets dimensions if you want to test some unortodhox shapes here and there, just know that these sizes I mentioned here are what's been proven to work nicely. Remember, you can always tweak the scale of top and bottom UI in the options.

- The assets are customizable, but the layout isn't! Maybe someday this might change, but for now, it is what it is.

- Vertical support still needs a bit of polish, but it does work.

- If you want your assets to look nice in game, regardless of the display size you're using, you should take in consideration the fact that this game's visuals are all based on pixel art meant to work on tiny screens with a very small resolution! Keep it simple, less is more, etc.

- Only works in Gen 1 for now! I do want to port it to Gen 2, but haven't found time to mess with it yet

- This mod was tested on PC (Windows 11), and Android. I don't have access to any iOS device, Linux or Switch to test things myself. If you're running on of those systems I couldn't test for, let me know how it goes!

- If you find any bugs, let me know, and I will do my best to help you out, but again, I'm not a developer. I made this with the help of AI because I wanted a specific experience for my playthrough that I couldn't find anywhere.

- If you want to fork this to do your own thing, go for it! Let me know what you have in mind for your version as well, and if I can help in some way!
