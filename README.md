*Disclaimer: I'm an artist, not a developer. All design choices, custom assets and ideas present in this mod are my own, but the code itself was written by Claude. No generative AI was used in the making of assets.*
*Also, this is my first mod. So if anything is out of place or wrong, please let me know!*

----

This is my mod, **Seto Battle UI**.
A different take on the classic battle HUD that aims to be fully customizable, even for people who have no experience with coding whatsoever. I couldn't find any mod for the battle UI that satisfied me 100%, so I tried to create my own. It features:

- EXP bar
- Indicator stating if the pokémon you're currently battling was already caught
- Move description
- Different move colors according to it's type
- Reworked menus (FIGHT, ITEMS, PKMN)
- Bag with different pockets to separate items into categories
- Adjustable toggles for scale, font size, and font color
- Detailed move comparisons when learning a new move after leveling up
- Theme support

The mod comes with some themes created by me, based on different pokemon games. I'm a sucker for customization, so theme support was something that I REALLY wanted to implement here. Here's a quick guide on how can you create a theme for this mod:

## 🎨 Creating a theme

Seto Battle UI detects themes automatically: every **folder** inside `assets/custom_ui/` becomes an option in the **BATTLE UI THEME** list (the folder name is shown in uppercase in the menu).

```
seto_battle_ui/
└── assets/
    └── custom_ui/
        └── MyTheme/          ← folder name = theme name
            ├── main_menu_bg.png
            ├── btn_fight.png
            ├── type_fire.png
            └── ...
```

### General rules

- All files are **PNG with transparency (RGBA)** and go **inside the theme folder**.
- File names must be **exactly** the ones listed below (lowercase, with `_`), since that is how the mod finds each asset.
- **No file is mandatory.** Any missing asset makes the mod fall back to the default look for that element, so you can build a theme piece by piece.
- Images are drawn with *nearest* filtering (no smoothing), which is ideal for pixel art. If you use a size different from the one listed, the image will be **stretched** to fit, so keep the **same aspect ratio** as the recommended size.
- **Automatic contrast:** the mod calculates the average luminance of the `*_bg.png` and `type_*.png` files. If the theme is dark, the text becomes light; if it is light, the text becomes dark. There is nothing to configure.
- The dimensions below are the recommended ones.

---

### 1. Panel and window backgrounds

| File | Dimensions (px) | Used for |
|---|---|---|
| `enemy_top_bg.png` | 97 × 34 | Top panel of the enemy Pokémon (name, level, HP) |
| `player_top_bg.png` | 97 × 34 | Top panel of your Pokémon |
| `main_menu_bg.png` | 296 × 48 | Background of the main battle menu (FIGHT / PKMN / ITEM / RUN) |
| `message_bg.png` | 296 × 48 | Battle message box |
| `moves_left_bg.png` | 184 × 48 | Left panel of the moves menu (move list) |
| `moves_right_bg.png` | 104 × 48 | Right panel of the moves menu (move details) |
| `bag_bg.png` | 272 × 112 | Bag screen background |
| `party_bg.png` | 272 × 112 | Party screen background |
| `summary_bg.png` | 272 × 112 | Summary screen background |
| `party_slot_bg.png` | 112 × 25 | Each Pokémon slot in the party list |
| `choice_bg.png` | 84 × 40 | YES/NO window and generic choice lists |
| `statsbox_bg.png` | 104 × 84 | Stats window shown on level up |
| `moveforget_bg.png` | 114 × 70 | Window listing the 4 current moves when forgetting a move |
| `moveinfo_bg.png` | 86 × 70 | A/B move comparison windows (the same file is used for both) |

### 2. Main menu buttons

| File | Dimensions (px) | Used for |
|---|---|---|
| `btn_fight.png` | 77 × 50 | FIGHT button |
| `btn_pkmn.png` | 77 × 50 | PKMN button |
| `btn_item.png` | 77 × 50 | ITEM button |
| `btn_run.png` | 77 × 50 | RUN button |

### 3. HP and EXP bars

Bars are built from layers: **track** (background, optional) → **fill** → **frame** (drawn on top, with a transparent center).

The `fill` is **not stretched**: it is **cropped from left to right** according to the current HP/EXP ratio. Because of this, draw the `fill` as the **100% full bar**, covering the whole file.

> ⚠️ **The HP bar assets only work if `hp_bar_frame.png` exists.** Without the frame, the HP bar is drawn by code and the other HP files are ignored.
>
> ⚠️ **The EXP bar assets only work if `exp_bar_frame.png` and `exp_bar_fill.png` are both present.** Without both, the EXP bar is drawn by code.

| File | Dimensions (px) | Used for |
|---|---|---|
| `hp_bar_frame.png` | 50 × 4 | HP bar frame (**required** for HP bar assets to work) |
| `hp_bar_track.png` | 50 × 4 | HP bar background (optional) |
| `hp_bar_fill_green.png` | 50 × 4 | Fill when HP is above 50% |
| `hp_bar_fill_yellow.png` | 50 × 4 | Fill when HP is between 25% and 50% |
| `hp_bar_fill_red.png` | 50 × 4 | Fill when HP is 25% or below |
| `exp_bar_frame.png` | 71 × 4 | EXP bar frame (**required**, together with the fill) |
| `exp_bar_fill.png` | 71 × 4 | EXP bar fill (**required**, together with the frame) |
| `exp_bar_track.png` | 71 × 4 | EXP bar background (optional) |

> All three EXP bar files must have **the same size as each other**.

### 4. Type tags (18 files)

All **63 × 13 px**. Shown on moves and information screens.

| File | File | File |
|---|---|---|
| `type_normal.png` | `type_fire.png` | `type_water.png` |
| `type_electric.png` | `type_grass.png` | `type_ice.png` |
| `type_fighting.png` | `type_poison.png` | `type_ground.png` |
| `type_flying.png` | `type_psychic.png` | `type_bug.png` |
| `type_rock.png` | `type_ghost.png` | `type_dragon.png` |
| `type_dark.png` | `type_steel.png` | `type_fairy.png` |

### 5. Status icons (5 files)

All **32 × 14 px**. Status condition abbreviations shown on the panels.

| File | Condition |
|---|---|
| `status_brn.png` | Burn |
| `status_par.png` | Paralysis |
| `status_psn.png` | Poison |
| `status_slp.png` | Sleep |
| `status_frz.png` | Freeze |

---

### 6. Global asset (outside the theme folder)

This file **does not belong to any theme**: it lives in the mod's `assets/` folder and applies to all themes.

| File | Dimensions (px) | Used for |
|---|---|---|
| `assets/evolution_bg.png` | 1920 × 1080 | Background of the evolution screen |

> ⚠️ This image is resized in *cover* mode to fill the entire game window, so it is **subject to distortion and cropping** depending on the display or window size used. Keep the important parts of the artwork away from the edges, and avoid details that break if stretched.

---

### Quick checklist

- [ ] New folder inside `assets/custom_ui/` named after your theme
- [ ] RGBA PNGs with the exact file names from the tables above
- [ ] Bar `fill` files drawn as a full bar
- [ ] Bar frames with a transparent center
- [ ] `hp_bar_frame.png` present if you want custom HP bars
- [ ] `exp_bar_frame.png` and `exp_bar_fill.png` both present if you want custom EXP bars
- [ ] Launch the game and pick your theme in **BATTLE UI THEME**


---

## Notes

- If you want your assets to look nice in game, regardless of the display size you're using, you should take in consideration the fact that this game's visuals are all based on pixel art meant to work on tiny screens with a very small resolution! Keep it simple, less is more, etc.

- Only works in Gen 1 for now! I do want to port it to Gen 2 and Gen 3, but haven't found time to mess with it yet

- This mod was tested on PC (Windows 11), and Android. I don't have access to any iOS device, Linux or Switch to test things myself. If you're running on of those systems I couldn't test for, let me know how it goes!

- If you find any bugs, let me know on the g1rdeluxe's discord, and I will do my best to help you out, but again, I'm not a developer. I made this with the help of AI because I wanted a specific experience for my playthrough that I couldn't find anywhere.

- If you want to fork this to do your own thing, go for it! Let me know what you have in mind for your version as well, and if I can help in some way!


---

## How to install

- Download the latest .zip file on the releases page
- Open G1Rdeluxe's launcher and click on "Mods"
- Click on "Import Mod.zip", and select the one you just downloaded

*Reminder: This was made for Gen 1 games (RBY), and was not tested on later titles.*
