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

# Zombie Night Terror v1.5.3

Internal cheat for **Zombie Night Terror v1.5.3** (Unity Mono, 32-bit).
Press **DEL** to open the menu, **T** spawns at the mouse.

## Features :

### Main
- **Infinite DNA** free specials, costs nothing
- **God zombies / God everything**  unkillable, auto re-applied to new spawns
- **Heal tick + DNA trickle**  constant sustain
- **Game speed**  0.1x–4x slider

### Mutate
- **Anytime re-mutate**  specials can change again anytime
- **Sticky unlocks**  HUD + paths stay unlocked across levels
- **Force all**  Tank / Crawler / Runner / Boomer / Screamer / Spit / Conta / Jump / Sacri / Overlord / Normal

### Powers
- **Scream / blast radius + damage**  sliders with INF toggles
- **Spit lab**  damage, speed, burst fire, mouse homing + strength, laser (no gravity)
- **Speed**  zombies x0.5–4, humans x0–3 (0 = frozen), blind humans
- **OHK humans**  damage x999 on humans only, zombies safe
- **Kill all humans**  one click

### Spawn
- **Type picker + T to spawn**  Copy / Normal / every special, right at the cursor
- **Spawn x5**  instant horde

### Level
- **No-fail**  zombie-death lose checks removed
- **Win now / complete challenge / unlock all levels / zoom unlock**
- Live readouts: DNA value + status line

## Usage
1. Start the game
2. Inject `ZNT_Cheat.dll`
3. Press **DEL** for the menu because we are going to add it here
