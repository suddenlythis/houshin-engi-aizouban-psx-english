# Installing the Houshin Engi Aizouban English translation (v1.0.1)

The download contains only the changes to the game's data track, not the game. You need your
own disc image of Houshin Engi - Aizouban (Japan), the Redump version.

## What you need

- The Redump version of **Houshin Engi - Aizouban (Japan)** (product code SLPM-86209): one
  `.cue` and one `.bin`, as Redump catalogues it.
- The file that gets patched must be exactly:

  | File | Size | SHA-1 |
  |---|---|---|
  | `Houshin Engi - Aizouban (Japan).bin` | 363,266,400 bytes | `81351d74a1623f65a83220bf313df4a36a953361` |

  With any other file the patch refuses to apply.
- xdelta3, or a front end for it such as Delta Patcher or xdelta UI. Rom Patcher JS in a web
  browser also applies `.xdelta` files.
- A PlayStation emulator. Tested on DuckStation.

## What is in the zip

| File | What it is |
|---|---|
| `HoushinEngi-EN-v1.0.1.xdelta` | The patch for the data track |
| `Houshin Engi - Aizouban (English).cue` | Optional cue sheet, only for the side-by-side alternative below. Most people do not need it |
| `README.txt` | The release notes |

## How to apply

Patch the `.bin` with the `.xdelta`. Keep the file name, and open your usual `.cue`. That is all.

### With Delta Patcher

1. Original file = your `Houshin Engi - Aizouban (Japan).bin`
2. XDelta patch = `HoushinEngi-EN-v1.0.1.xdelta`
3. Tick Backup original file in the settings, then Apply patch.

### With the command line

xdelta3 writes a new file, so rename the original first:

```
ren "Houshin Engi - Aizouban (Japan).bin" "original.bin"
xdelta3 -d -s "original.bin" HoushinEngi-EN-v1.0.1.xdelta "Houshin Engi - Aizouban (Japan).bin"
```

### Check the result

The patched file is 363,266,400 bytes with this SHA-1 checksum:

| File | SHA-1 after patching |
|---|---|
| `.bin` | `97a7aae7c3fdb5742a701ee7abfbe74eccc1aeae` |

## Alternative: keep the Japanese and English discs side by side

Leave your files alone, save the patched file as `Houshin Engi - Aizouban (English).bin` in
the same folder, and open `Houshin Engi - Aizouban (English).cue` from the zip.

## After patching

Start a new game or load an in-game save. A save state made on the Japanese game keeps the old
program and text in memory, so load the game normally instead. In-game saves (memory card) work
with both versions.

Controls: Circle confirms and advances text, Cross cancels, Triangle shows the turn order in
battle, L1 / R1 rotate the map, L2 zooms and R2 tilts it. If the game does not react to the pad,
set the controller type to Digital Controller.

## Tested on

DuckStation. Not tested on other emulators or on real hardware.
