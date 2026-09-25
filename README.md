# Cheat-Hobby
thanks for dropping by in this repo. It's just a nerd session where I hack games, dive in a rabbit hole of reverse Engineering, Game Hacking, and maybe Website exploit/bug hunt


# TJOC_Story_Mode Incomplete

## Goal :

Fix Noclip.

Improve ESP (probably just make it Text ESP depending on the Level).

Make animatronic stupid (semi complete).

Internal cheat for **The Joy of Creation: Story Mode** (UE 4.16.2, DX11).
Press **DEL** to open the menu.

## Features :

### Visual
- **Full Brightness**  adjustable strength slider to light up dark scenes

### Bedroom
- **Freeze sanity**  sanity pinned at a slider value, never drains
- **No jumpscares**  freezes the AI schedule and zeroes the scare flags
- **Lamp always on**
- **Fast clock**  0.5 s per hour instead of 110 s
- **Skip to 5 AM**  finish the night instantly 
- Live readouts: sanity value + current hour

### Living Room
- **No jumpscares**  freezes Bonnie/Freddy/Foxy stages, cuts Chica's collision
- **No clip**  fly mode with no collision, straight through walls

### ESP
- Boxes, names and distance on all animatronics and players
- Covers Living Room, office and bedroom variants
- Works through the dynamically discovered game camera

### Extras
- **F9 dump**  writes a full object/property dump to `ue_dump.txt`
- Dumper-7 SDK included (press F8 in-game) for offset research
- Everything logs to `imgui_log.txt` for debugging

## Usage
1. Start the game
2. Inject `TJoC_Internal_Fixed.dll`
3. Press **DEL** for the menu
