ZNT Cheat — IMGUI menu (DEL)
==============================
Game : Zombie Night Terror v1.5.3 (32-bit, Mono)
File : ZNT_Cheat.dll (v3, net472, Unity-only refs + reflection, no hard game ref)

v3 adds: anytime re-mutate (CanMutate tick + unlock all paths/cost 0 + force all zombies
to Tank/Crawl/Run/Boom/Scream/Spit/Conta/Jump/Sacri/Over/Normal via Mutate(...,false)),
scream radius slider+inf (ScreamAsset.Radius + live SphereDetection), blast radius/damage
sliders+inf (ExplosionAsset.DamageRadius/TileRadius/Damage + live ExplosionEffect),
spit damage/speed sliders (SpitMutation Basic/Crawler/Overlord/Tank .Damages.Damage,
.SpeedModifier), burst spit (SpitMenu.closeOnApply=false tick), steer spit homing,
zombie melee damage slider+inf (Attacker.Damage, zombies only).

v4: tabbed menu (Main/Mutate/Powers/Spawn/Level, DEL toggles, drag by title bar).
Spawn tab: pick type (Copy/Normal/Tank/Crawler/Runner/Boomer/Screamer/Spit/Conta/
Jump/Sacri/Overlord), Spawn L/R buttons or hotkey T spawn the picked type at the
mouse cursor (needs 1 live zombie in the level to clone from; specials arrive
pre-mutated via Mutate(...,false)). Spawn x5 for a quick horde.

v5: spawner fixed via game factory (ZombieAsset.CreateGameObject + OnSpawn, no more
shared-mutation clones; clone fallback resets + rebuilds the original's build).
Mutate tab: STICKY unlocks toggle (HUD top-up + paths re-applied silently every
0.5s tick, survives level changes). Main: game-speed slider (TimeManager.
ForceTimeScale 0.1-4x). Powers: KILL ALL HUMANS (Health.Kill force, zombies
skipped).

v6: Main: DNA trickle (+15/tick). Powers: zombie speed x0.5-4, human speed x0-3
(0 = frozen solid), blind humans (vision Distance ~0, originals restored on
untoggle), OHK humans (DamageMultipliers x999 on humans/props only, originals
restored), spit homing-strength slider, laser spit (GravityScale 0 on rigs +
live projectiles). Level: NO-FAIL (drops zombie-count/escape lose checks, win
path untouched), Complete challenge button, zoom unlock (0.5-40).

MENU
----
Press DEL (Delete) in-game to show/hide. Window drags by title bar.

- Infinite DNA / free specials : MutationSelector.InfiniteDna + SetDnaInfinite + DnaBar.SetInfinite
  Normal -> Tank / Crawler / Runner / Boomer / Screamer / Spit / etc. costs nothing.
- God mode : sets Health.Invincible=true + RestoreHp on every Health, re-applied 2x/sec for new spawns.
- Constant heal tick : RestoreHp loop.
- Unlock ALL mutations : UnlockMutation(type, 99) for every MutationType.
- Give MAX DNA : DnaMax=9999, Dna=Max + GainDna.
- Heal all / Spawn L / Spawn R (CheatManager.SpawnZombieLeft/Right at mouse) / Unlock ALL levels (PlayerProgression.UnlockAllLevels) / Win level now (GameManager.OnWinLevel).

INJECT (SharpMonoInjector, x86 — game is 32-bit)
------------------------------------------------
1. Run znt.exe, get to main menu / load a level.
2. Open SharpMonoInjector GUI (use the x86 build):
   Process  : znt.exe (or inject by process name "znt")
   Assembly : D:\Games\Zombie.Night.Terror.v1.5.3\ZNT_Cheat.dll
   Namespace: ZNT_Cheat
   Class    : Loader
   Method   : Init
   Click Inject.
   Console version:
     smi.exe inject -p znt -a "D:\Games\Zombie.Night.Terror.v1.5.3\ZNT_Cheat.dll" -n ZNT_Cheat -c Loader -m Init
3. Press DEL. If MutationSelector says "load a level", enter any level first — singletons only exist in-level.
4. Eject: call ZNT_Cheat.Loader.Unload, or just close the game.

NOTES
-----
- Re-applied on a 0.5s tick so newly spawned zombies stay godded / free while toggles are on.
- Turning Infinite DNA off restores normal costs; turning God off sets Invincible=false on current objects.
- Source: C:\Users\Jeshua\AppData\Local\Temp\opencode\ZNT_Cheat\Cheat.cs — rebuild with: dotnet build ZNT_Cheat.csproj -c Release
- Permanent alternative (no injector): dnSpy patch MutationSelector.ConsumeDna => return; + Health.ReceiveDamage => return; then save module.
