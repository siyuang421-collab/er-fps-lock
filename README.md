# Elden Ring — FPS Patch + Position-Trigger Auto FPS Lock

A [Cheat Engine](https://cheatengine.org/) table for **Elden Ring** speedruns.
It adds automatic FPS switching based on your in-game position, on top of a
manual FPS limit.

## Features

- **FPS Patch** — lock the game to a custom frame rate (20–60 FPS) via the
  injected DLL symbols `ER_FPS_PATCH_ENABLED` / `ER_FPS_CUSTOM_LIMIT`.
- **Position-Trigger Auto FPS Lock** — define up to 80 points. Walk near an
  *open point* to apply a custom FPS, walk near a *close point* to restore the
  game's native limit.
- Per-point FPS, batch add/delete, tick a row to delete it, double-click a row
  to change its FPS.
- FPS Patch and Position Trigger are **mutually exclusive** — enabling one
  while the other is active refuses with a prompt.
- Points persist to a text file across CE restarts and game sessions.
- Resets to native FPS when you close CE.

## Files

| File | Language |
|------|----------|
| `er-patched-fps-compact-EN.CT` | English UI |
| `er-patched-fps-compact.CT` | Chinese UI |

The two files share the same save data on disk.

## Requirements

- Cheat Engine 7.x
- The matching injected DLL exposing `ER_FPS_PATCH_ENABLED` (byte) and
  `ER_FPS_CUSTOM_LIMIT` (float). The table attaches to `eldenring.exe`
  automatically and shows `WAIT` until the symbols are ready.

## Usage

1. Inject your DLL and attach CE to `eldenring.exe`.
2. Open the `.CT` file.
3. **Manual:** tick `FPS Patch [OFF]`, then double-click the `FPS Limit` row
   and enter a value (20–60).
4. **Position trigger:** tick `Enable Position Trigger [OFF]`, then:
   - `➕ Add Open Point` — save current location with a custom FPS
   - `➕ Add Close Point` — save current location to restore native FPS
   - `✏ Set FPS` — change an open point's FPS
   - `🗑 Clear All Points` — wipe all points
   - `Trigger radius (m)` — click to change detection radius (default 5)
5. Tick a row in the open/close list to delete that point; double-click an
   open-point row to edit its FPS.

## Where points are saved

```
%USERPROFILE%\EldenRingFps\er_fps_save.txt
```

e.g. `C:\Users\<you>\EldenRingFps\er_fps_save.txt`. The table shows this path
in the `Points saved to:` row. To share points with someone, copy that `.txt`
into the same folder on their machine.

## Notes

- Map IDs must match exactly (SoulSplitter format, e.g. `m11_00_00_00`);
  points trigger by 3D distance within the radius, only on the same map.
- This is a personal speedrun tool, provided as-is.
